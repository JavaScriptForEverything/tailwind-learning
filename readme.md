## Setup `Tailwind` for regular project

```
$ yarn init -y
$ yarn install -D tailwindcss

$ yarn tailwindcss --help 		: Get use arguments

$ yarn tailwindcss init 		: Create Tailwind Config file
```


#### /src/tailwind.css : 
- Style File which will be used to compiled

```
@tailwind base; 			: import base 	styles
@tailwind components; 			:   " 	components  "
@tailwind utilities; 			:   " 	utilities   "
```



#### Compile pure CSS from tailwind CSS 	:

```
$ yarn tailwind --input ./src/tailwind.css --output ./build/tailwind.css
```


#### Put the compiler command to script `package.json`
```
{
	"scripts": {
		"tailwind": "tailwindcss --input ./src/tailwind.css --output ./build/tailwind.css --watch"
	},
  	"devDependencies": {
    		"tailwindcss": "^3.2.4"
  	}
}
```

#### Compile Tailwind CSS to pure CSS
```
$ yarn run tailwind 			: Create ./build/tailwind.css from ./src/tailwind.css file
```


#### Add build styles into HTML file

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">

	<link rel="stylesheet" href="./build/tailwind.css">
	<title>Tailwind CSS</title>
</head>
<body>
	
	<div class="w-32 h-32 bg-gray-900 m-12 text-white">Hello</div>
	
</body>
</html>
```

#### VSCode Settings for Tildwind
- install `Tailwind CSS IntelliSense`
- .vscode/settings.json
```
{
	"css.validate": false,
	"tailwindCSS.emmetCompletions": true
}
```