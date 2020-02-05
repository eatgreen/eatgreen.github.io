```js
typedef bool (*pfcnValidate)(int, int);
bool (*bingo)(int,int);   -is equivalent to-   pfcnValidate bingo;

ALSO, 
bool validate(int a, int b, bool (*bingo)(int,int));    
-is equivalent to-   
bool validate(int a, int b, pfcnValidate bingo); 

typedef int myinteger;
typedef char *mystring;
typedef void (*myfunc)();
 
myinteger i;   // is equivalent to    int i;
mystring s;    // is the same as      char *s;
myfunc f;      // compile equally as  void (*f)(); 
 
typedef int (*t_somefunc)(int,int);

int product(int u, int v) {
  return u*v;
}

t_somefunc afunc = &product;
...
int x2 = (*afunc)(123, 456); // call product() to calculate 123*456

In lbfgs:

typedef lbfgsfloatval_t(* lbfgs_evaluate_t)(void *instance, 
                                            const lbfgsfloatval_t *x, 
                                            lbfgsfloatval_t *g, 
                                            const int n, 
                                            const lbfgsfloatval_t step)
                                            
so 
lbfgsfloatval_t(* evaluate)(void*, const lbfgsfloatval_t*, lbfgsfloatval_t*, const int, const lbfgsfloatval_t);
-is equivalent to-   
lbfgs_evaluate_t evaluate;

But you can not declare something directly as this, but rather declare something like
lbfgsfloatval_t  _evaluate{void*, const lbfgsfloatval_t*, lbfgsfloatval_t*, const int, const lbfgsfloatval_t};
```