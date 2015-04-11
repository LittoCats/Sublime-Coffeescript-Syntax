## Coffeescript .tmLanguage 

![Coffeescript](http://i.imgur.com/zj6q7yS.png)

This is built off of [Better CoffeeScript](https://packagecontrol.io/packages/Better%20CoffeeScript).


### Features
- Adds function call highlighting scope `meta.function-call.coffee`
This includes `fn 1`, `fn(1)`
	```
	fn ++something
	fn( {something: 1} )
	fn  
		something: 1
	```
- Removes a lot of variable assignment scopes that cannot be always gauranteed.
In this example, `something` can't be detected with `.tmLanguage` hightlighting
```coffee
{
	something
} = stuff
```
There are many more instances of this. The philosophy is that everything is a variable until specified otherwise. Object keys for example are kept.
- Dots in `some.thing.here()` are always highlighted, in parameter lists etc.
- `{}[]().=>->""''` characters are ensured scopes
- Adds JSX highlighting.
	+ Not 100% complete but works for most cases at the moment. Some nesting scenarios produce bad highliting, need to look into it further.

### Install
- Clone this repo into `./Data/Packages/`.
- Select this `CoffeeScript` for your CoffeeScript files in the statusbar's dropdown.
- To use this `.tmLanguage` alongside another addon; simply replace it. With packaged apps this would mean creating the path `./Data/Packages/Better CoffeeScript/CoffeeScript.tmLanguage` (Thus overwriting the file inside the package in `./Data/Installed Packages/` package). There may be an easier way but I have found trying to co-habitat with two identically named synates results in this one reverting.

### Further work
- I will eventually rewrite the whole thing using the new YAML ST3 highlighting syntax which apparently allows for more flexibility. This should ensure better coverage.
