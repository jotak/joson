joson
=====

My json lib

This is a minimalist C++ library aiming to provide easy json reading.

Example :


string sError;

JoSon * jsonPtr = JoSon::fromString(string("{a:1, b:[2, 3, \"toto et tata\"], c : foo, f:[9,8,7,8,9]}"), &sError);

JoSon& json = *jsonPtr;


assert(json.isMap());

assert(json["a"].isLeaf());

string a = json["a"].toString();

assert(a == "1");

assert(json["b"].isList());

assert(json["b"][0].isLeaf());

double b0 = json["b"][0].toDouble();

assert(b0 == 2.0f);

assert(json["b"][1].isLeaf());

int b1 = json["b"][1].toInt();

assert(b1 == 3);

assert(json["b"][2].isLeaf());

string b2 = json["b"][2].toString();

assert(b2 == "toto et tata");

assert(json["c"].isLeaf());

string c = json["c"].toString();

assert(c == "foo");

assert(json["d"].isNull());

string d = json["d"].toString();

assert(d == "");

assert(json["e"][9].isNull());

int e = json["e"][9].toInt();

assert(e == 0);

