você pode rodar com:  
`npx webpack`

pode também:  
`npx webpack --config webpack.config.js`  

e usando npm:  
`npm run build`  

o arquivo **package.json** possui a configuração para o npm rodar o **webpack**:  
```javascript
  "scripts": {
    "build": "webpack"
  },
```

se o **webpack** for instalado de forma global:  
`npm install webpack -g`  

então é só chamar com:  
`webpack`  

O **webpack** por padrão não aceita css, e nenhum outro formato a não ser js

Esse projeto só aceita js e css

Para ele aceitar css foi necessário seguir os seguintes passos:  

adicionar os módulos npm:  
**style-loader** para adicionar os css numa tag <style>   
**css-loader** para compactar todos os css num JSON no bundle:  
`npm install --save-dev style-loader css-loader`  

é necessário adicionar um import para o css:  
`import './style.css';`

e adicionar os módulos npm no **webpack.config.js**:  
```javascript
  module: {
    rules: [
      {
        test: /\.css$/,
        use: [
          'style-loader',
          'css-loader',
        ],
      },
    ],
  },
  ```