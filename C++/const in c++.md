copy constructor:
envar(const envar& rhs) {...}

copy assignment operator
envar& operator=(const envar& rhs)

If an operator is reloaded with const parameters, when calling it, arguments must be const as well.