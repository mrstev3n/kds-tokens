## Project setup
Starting with blank project
```
git init
```

```
npm init -y
```
## Start a javascript project

### React example :

```
npx create-react-app my-app
cd my-app
npm start
```

### Install Style dictionary
> See [More about Style dictionary](https://github.com/amzn/style-dictionary).
```
npm install -D style-dictionary
```

### Install Token transformer for Figma Tokens Plugin
> Since style dictionary can't read alias on json file generated from figma token plugin, we need this package to transform the generated json to a readable json for style dictionary - > See [A discussion about it](https://github.com/amzn/style-dictionary/issues/773#issuecomment-1049641683).

```
npm i -D token-transformer
```

### Write a script to initialize a style dictionary

>Let's define our `input` and `output` json name first. Nowing that the `output` is the json from the figma plugin and the `input` a transformed version usable by style dictionary (which strips away the set keys).
> - input: `mytoken.json` 
> - output: `mytoken-min.json`


Go to `package.json` and add this to the sript{}  section

```
, "init-dict" : "style-dictionary init basic"
, "builder" : "style-dictionary build"
```

### Run the script & edit config file

```
npm run init-dict
npm run builder
```

- add `build` folder name to .gitignore
- remove tokens folder content and replace by your `output`

so go from this

├── tokens/
│   ├── size/
│       ├── font.json
│   ├── color/
│       ├── font.json

to this

├── tokens/
│   ├── mytoken.json


### Write a script to transform output & fix alias

Go to `package.json` and add this to the sript{}  section

```
,"transformer": "token-transformer tokens/mytoken.json tokens/mytoken-min.json"
```

Also edit builder script by inseting a run for transformer

```
,"builder" : "npm run transformer && style-dictionary build",
``` 

- go to `config.json` and replace all with :

```
{
  "source": ["tokens/mytoken-min.json"],
  "platforms": {
    "scss": {
      "transformGroup": "scss",
      "buildPath": "src/scss/",
      "files": [{
        "destination": "_variables.scss",
        "format": "scss/variables"
      }]
    }
  }
}
```
- now run :

```
npm run builder
```

>notice than this command will generate a new json file to the tokens folder

├── tokens/
│   ├── mytoken-min.json
│   ├── mytoken.json


_

_

---

### Compiles and hot-reloads for development (Reactjs)
```
npm start
```

### Lints and fixes files
```
npm run lint
```
or
```
npm run lint -- --fix
```

## License

[MIT License](LICENSE)