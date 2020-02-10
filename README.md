# postman-tests

A seguir é exemplificado alguns exemplos de scripts de testes no postman

### Verifica os valores vindo do response body(JSON) da requisição
```js
pm.test("Título do teste", function () {
    // recupera o json da resposta a requisição
    var jsonData = pm.response.json();
    // compara o atributo a um valor
    pm.expect(jsonData.nome).to.eql("Joãozinho");
});
```
### Verifica status code da resposta a requisição
```js
pm.test("Codigo do status é 200", function () {
    // Podemos testar outros status como: 400, 500...
    pm.response.to.have.status(200);
});
```
### Verifica se a resposta possui uma string
```js
pm.test("Body possui string", function () {
    pm.expect(pm.response.text()).to.include("String que você procura");
});
```
### Verifica se o body com a resposta possue exatamente a string
```js
pm.test("Body possui a string", function () {
    pm.response.to.have.body("string esperada que venha no body");
});
```
### Verifica se no headers há um Content-type específico
```js
pm.test("Headers possui Content-Type", function () {
    pm.response.to.have.header("Content-Type");
});
```
### Verifica se o tempo da resposta para a requisição é "menor que"
```js
pm.test("Response time is less than 200ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(200);
});
```

[Referência](https://learning.postman.com/docs/postman/scripts/test-scripts/)
