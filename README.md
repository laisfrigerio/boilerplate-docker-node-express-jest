# docker + node 18 + express + jest and supertest

A docker boilerplate with node 18 + express + jest + supertest 💜

## 🛠️ Stack

- nodejs: 18 + express
- jest
- supertest
- docker

### Docker version

We develop this boilerplate with the following docker version: `20.10.22`

## :pencil: Features

- :ballot_box_with_check: nodejs 18 + express api
- :ballot_box_with_check: test setup with `jest` + `supertest`
- :ballot_box_with_check: running integration tests with docker
- :ballot_box_with_check: running this application with docker

## :gem: Run application

```bash
    npm run docker:build
    npm run docker:run
```

- Open a browser and type the following URL: `http://localhost:49127`

## :gem: Run tests

```bash
    npm run docker:build
    npm run docker:test
```

## :gem: How add eslint

1. Install eslint:

```bash
    npm install eslint -D
```

```bash
    yarn add eslint -D
```


2. Let's generate the `.eslintrc.json`:

```bash
    npx eslint --init
```

```bash
    yarn eslint --init
```

This command promotes you to multiple options, choose the following options:

1. To check syntax and find problems, and enforce code style
2. JavaScript modules > `commonjs`
3. Does your project use TypeScript No/Yes In my case, I am not using TypeScript > `No`
4. Where does the code run? > `Node`
5. What format of the config file? > `JSON`
6. Would you like to install them now with npm? > In my case, I am not using npm `No`

After finishing these promote options, a `eslintrc.json` file will be created with the following configuration:

```json
{
  "env": {
    "browser": true,
    "commonjs": true,
    "es2021": true
  },
  "extends": "eslint:recommended",
  "parserOptions": {
    "ecmaVersion": 12
  },
  "rules": {}
}
```

3. ESlint rules:

We will add additional eslint rules to this file. So you can override the entire content of this file with the following:

```json
{
    "env": {
        "browser": true,
        "commonjs": true,
        "es2021": true,
        "jest": true
    },
    "extends": "eslint:recommended",
    "overrides": [
    ],
    "parserOptions": {
        "ecmaVersion": "latest"
    },
    "rules": {
        "indent": [
            "error",
            2
        ],
        "no-mixed-spaces-and-tabs": "warn",
        "linebreak-style": [
            "error",
            "unix"
        ],
        "quotes": [
            "error",
            "single"
        ],
        "semi": [
            "error",
            "always"
        ],
        "no-unused-expressions": [
            "error",
            {
                "allowTernary": true
            }
        ],
        "no-unused-vars": [
            "error",
            { 
                "argsIgnorePattern": "request|response|next|__"
            }
        ],
        "space-infix-ops": "error",
        "space-unary-ops": "error",
        "no-multiple-empty-lines": [
            "error", 
            {
                "max": 2, 
                "maxEOF": 1
            }
        ],
        "no-whitespace-before-property": "error",
        "object-property-newline": [
            "error",
            { 
                "allowAllPropertiesOnSameLine": true
            }
        ],
        "space-before-function-paren": [
            "error", 
            "always"
        ],
        "arrow-spacing": [
            "error", 
            { 
                "before": true, 
                "after": true
            }
        ],
        "space-before-blocks": [
            "error", 
            "always"
        ]
    }
}
```

4. Run tests with `jest`

I just added `"jest": true` to env, because I want to apply unit testing using jest to our node project. Extra rules were added to the rules section as well.

## :woman: Author

[@laisfrigerio](https://instagram.com/laisfrigerio/)

## 📄 License

This project is licensed under the MIT License - see the LICENSE.md file for details