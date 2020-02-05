Using const reference parameter whenever possible. 
& is essentially another alias for the argument. 
without const, any change in the function body directly changes the objects to which the argument refers. 
 
Top-level const: 
right-most const is top level, the object itself is const.

int& means a function returns the reference.