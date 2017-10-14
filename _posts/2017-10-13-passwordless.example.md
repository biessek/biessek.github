---
layout: post
title:  "Autenticação sem senha (Passwordless)"
last_modified_at:   2017-09-28 21:00:00 -0300
date:   2017-09-28 21:00:00 -0300
categories: 
    - Desenvolvimento    
tags: 
    - desenvolvimento 
    - autenticação
    - vuejs
---
none
> Pequeno exemplo de autenticação sem senha utilizando o Facebook Account Kit no framework vuejs

### Requisitos:    
-   [npm](https://www.npmjs.com/package/npm)
-   [vue-cli](https://github.com/vuejs/vue-cli)
-   [vue-facebook-account-kit](https://github.com/biessek/vue-facebook-account-kit)

#### Criar aplicativo no facebook e habilitar Account Kit
- Criar o aplicativo no [facebook](developers.facebook.com)  
![criar o aplicativo no facebook](assets/images/passwordlessex/create-fb-app.png)  
{:.imgfb style="width: 500px"}
- Habilitar e configurar o account kit  
![configurar account kit](assets/images/passwordlessex/configure-account-kit.png)
{:.imgfb style="width: 500px"}
Para configurar, além das configurações padrão foi adicionado a url de callback do login  
![callback account kit](assets/images/passwordlessex/configure-callback.png)
{:.imgfb style="width: 500px"}

#### Criar cliente web para login com Account Kit
```bash
vue init webpack-simple passwordless-example
```
> inicializa um projeto vuejs utilizando [webpack](https://webpack.github.io/).

```bash
npm install
```
> Instala as dependências básicas de um projeto vue
```bash
npm install --save vue-facebook-account-kit
```
> Instala a biblioteca que vai carregar o account kit no app.

Após tudo instalado o código que dispara o login é o seguinte:
*main.js*
```javascript
import Vue from 'vue'
import App from './App.vue'
import AccountKit from 'vue-facebook-account-kit'

Vue.use(AccountKit)

new Vue({
  el: '#app',
  render: h => h(App)
})
```
> No main.js apenas carregamos o plugin.

*App.vue*
```javascript
<template>
  <div id="app">
    <facebook-account-kit ref="accountKit"
      appId="193014614575624"
      version="v1.0"
      :fbAppEventsEnabled='true'
      :debug='true'
      state="somecrsf">
      <input value="+1" id="country_code" v-model="countryCode" />
      <input placeholder="phone number" id="phone_number" v-model="phoneNumber"/>
      <button @click="login(countryCode, phoneNumber)">Login via SMS</button>
    </facebook-account-kit>
  </div>
</template>

<script>
export default {
  name: 'app',
  data() {
      return {
      countryCode : '+1',
      phoneNumber: ''    
    }
  },
  methods: {
    login (countryCode, phoneNumber) {
      console.log(this.$refs)
      this.$refs.accountKit.login({
        countryCode: countryCode, 
        phoneNumber: phoneNumber,
      }, this.loginCallback)
    },
    loginCallback (response) {
      console.log(response)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
```
> **template**, o componente é inicializado com os parâmetros necessários, apenas com um botão que vai disparar o login mandando os dados de código de país e número de telefone.

> **login**, o método de login é disparado e exibe a janela do sdk, que retorna ao `loginCallback` quando o processo for finalizado, apenas exibo um log para validar a comunicação.

### O código deste exemplo está disponível no [github]()

Referências:   
[https://www.npmjs.com/package/npm](https://www.npmjs.com/package/npm)
[https://github.com/vuejs/vue-cli](https://github.com/vuejs/vue-cli)
[https://github.com/biessek/vue-facebook-account-kit](https://github.com/biessek/vue-facebook-account-kit)