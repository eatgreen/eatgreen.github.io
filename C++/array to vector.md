This is how one converts an array to a vector as part of the vector definition:

std::vector<int> v(num1, num1+4);

This is how one converts an array to a vector not as part of the vector definition:

std::vector<int> v;
v.assign(num1, num1+4);