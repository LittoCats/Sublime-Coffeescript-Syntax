## Coffeescript .tmLanguage 

![Coffeescript](http://i.imgur.com/zj6q7yS.png)

- Adds function call highlighting scope `meta.function-call.coffee`
	+ This includes `fn 1`, `fn(1)`
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
