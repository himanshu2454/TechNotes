# Generics

```
    Generics allows us to create classes & methods decouple from data type
    Generic class are extensively used in generics collection classes
```

**Use Case -**
Let's say we have normal class which contains a method **AreEqual**, here the data type of parameter is fixed therefore
we can implement this methods for a single data type only.


```js
    public class NormalClass {

        //Can support one data type at a time either int or string .. for both the params.
        public static bool AreEqual(int x , int y){
            return x==y;
        }

        //As a workaround we can use "Object" data which base class for all the data types.
        public static bool AreEqual(object x , object y){
            return x==y;
        }

        //Generic Implementation
        //Data type is calculated on compile time; generalised implised implementation valid for
        //all data types.
        public static bool AreEqual<T>(T x , T y){
            return x.Equals(y)
        }

    }

    //Non-Generic Implementation
    AreEqual(1,2) // valid
    AreEqual("a","b") // Invalid

    //Non-Generic work-around
    AreEqual("a","b") //valid
    AreEqual(1,2)     //valid
    AreEqual(1,"b")   //valid

    //Issue with using object is -
    1. boxing & unboxing, as every time data is coverted to object type(boxing)
    2. No strick type checking; As seen 3rd example even in compatible data types can be passed
```