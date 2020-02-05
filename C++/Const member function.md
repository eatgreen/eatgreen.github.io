**const int& cod(void) const{ return cod_;}**
1. The second const after the parameter list and before the function body is actually the keyword for defining a const member function.
2. The first const means the function return value is of const type.
3. non-const object can call both const, non-const member function while the const object can only call const member function.
4. The object of const is to modify the type of the implicit this pointer.