###class Parameter contains all the parameters.

###class Dynobs contains general dynamic and observation variables and methods.
1. The construtor allows to construct either dynamic-grid or observation-grid configs
2. **Dynobs** is an abstract class because the function *TimeIntegration2D* is left as pure virtual function. The reason to do that is class **ShallowWater** is a derived class of **Dynobs** which inherites the variables and methods of **Dynobs**. The *runmodel* method defined in **Dynobs** is designed to be enough general in order to overload different *TimeIntegration2D* of each model.

###class ObsSynth contains variables and methods for creating synthetic observations.
1. **ObsSynth** is a derived class of base class **Dynobs**. It loads common constructor as **Dynobs**.

###class ShallowWater contains the dynamic model.
1. **ShallowWater** is a derived class of base class **Dynobs**. It loads common constructor as **Dynobs**.

###class Dataassim


###class Ensemble