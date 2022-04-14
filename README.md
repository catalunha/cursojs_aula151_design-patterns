# npm init

```
$ npm init -y
```
# ts
ts é uma linguagem compilada. js é uma linguagem interpretada.
```
$ npm install typescript -D
```
o tsconfig pode ser feito a mao ou com 'tsc init' 

Parece que o npx executa aplicativos do node_modules/.bin

Se digitar `$ npx tsc` ele vai compilar  codigo ts de `./src/index.ts` e jogar js resultado em `./dist/index.js`
Ai usando  `$ node index.js` executamos o js de dentro da pasta `./dist/index.js`


# ts-node
```
$ npm install ts-node -D
```
O `$ npx ts-node` executa o ts como o js. Ou seja ele compila e executa.

# configurando o coderunner
criar pastas `.vscode` e configurar com este conteudo
```js
{
  "code-runner.executorMap": {
    "javascript": "node",
    // "typescript": "ts-node",
    "typescript": "npx ts-node",
  }
}
```
assim o coderunner nao vai executar o ts com o ts-node global no computador mas sim com o `./node_modules/.bin/ts-node` usando o projeto atual.
Desta forma posso clicar em > do coderunner e execcutar o ts direto.


# eslint
no arquivo deste tipo
```js
module.exports = {
  env: {
    browser: true,
    es6: true,
    node: true,
  },
  extends: [
    'eslint:recommended',
    'plugin:@typescript-eslint/eslint-recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:prettier/recommended',
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 11,
    sourceType: 'module',
  },
  plugins: ['@typescript-eslint'],
  rules: {},
};
```
falta instalar o eslint e suas extends assim
`$ npm install -D eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser prettier eslint-config-prettier eslint-plugin-prettier`

mudar também no settings padrao do vscode:

```
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true,
        "source.fixAll": true
    },
    "code-runner.clearPreviousOutput": true,
```