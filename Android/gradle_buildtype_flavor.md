# Buildtype & productsFlavor in Gradle 

It's interesting to use gradle to define a lot of tasks or properties of your build.

firstly ,

we have buildType like 
```
buildTypes {
        release {
            // do something
        }
        debug {
            // do something 
        }
    }
```

and can define productsFlavors like 
```
productFlavors {
        demo {
            // do something
        }
        full {
            // do something
        }
    }
```

the build variant name follows *<product-flavor><Build-Type>* </br>
so we get 
```
demoRelease
demoDebug
fullRelease
fullDebug
```

---
## tips
* if run **gradlew assembleDebug** in terminal, it'll run compileDemoDebug and compileFullDebug, also can try to run **gradlew assembleDemo**
* be aware of 
  * **variant.getFlavorName**: get the real flavor name in current variant, we can use it to set properties of same flavor
  * **variant.mergedFlavor**: not clear
  * **variant.productFlavors**: get floavor list related to the buildType of current variant 
