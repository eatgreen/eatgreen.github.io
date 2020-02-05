1. scope, the scope of a derived class is nested inside the scope of its base class.
2. derived class constructor should not initialzie the base class members. primer. p. 598
3. The reason why we can use an object of derived type (or reference/pointer) when a reference to the base class is required: the derived object in mempry consisting two parts, base part and derived part.

###Conversion###
we can bind reference of base class type to an object of derived type.
The static type and the dynamic type of an object (non reference/pointer) is always the same, whereas the dynamic type of a reference/pointer may not be the same as the static type.