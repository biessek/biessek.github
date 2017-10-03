---
layout: post
title:  "Websockets"
last_modified_at:   2017-10-03 12:00:00 -0300
date:   2017-10-02 21:00:00 -0300
categories: 
    - Desenvolvimento        	
tags: 
    - desenvolvimento     
    - web
---

Websocket é uma tecnologia para navegadores com suporte a HTML5, que permite a comunicação bidirecional entre cliente-servidor com maior velocidade como principal benefício.

#### Benefícios:

- **Canal full-duplex**, (bidirecional) entre cliente-servidor. 
- **Conexão persistente**, ambos os lados podem enviar dados a qualquer momento.
- **API simples**, facil implementação, e suporte e praticamente todas as linguagens backend modernas.

Além disso o protocolo agora é  **padronizado IETF/RFC 6455**, amplificando sua utilização e adoção.

Para desenvolvedores que já trabalharam ou trabalham com desenvolvimento Desktop, o conceito é muito simples e já conhecido, a ideia é a mesma para web, apenas em proporções diferentes.

### vs HTTP
A única relação do protocolo `ws:` com o HTTP é a abertura do socket, através de uma requisição http o cliente solicita ao servidor uma abertura do canal, comando conhecido como `Upgrade`.
--------------------------
![processamento vs o HTTP](assets/images/websocketsvshttp.jpg)
{:.imgreg style="width: 500px"}
<span>Fonte: [Fabio Tiriticco](https://pt.slideshare.net/FabioTiriticco/websocket-wiith-scala-and-play-framework)</span><br>
--------------------------

Dá para observar a diferença no desempenho, isso porque o websocket gera um menor overhead no servidor, são menos requisições que ele tem que atender, básicamente um canal sob-demanda de alta velocidade.

![websocket vs http](http://devcentral.f5.com/weblogs/images/devcentral_f5_com/weblogs/macvittie/Windows-Live-Writer/HTML5-WebSockets-High-Speed-Integration-_44D0/http-versus-html5ws_thumb.png)
{:.imgreg style="width: 500px"}
<span>Fonte: [DevCentral](https://devcentral.f5.com/articles/html5-websockets-high-speed-infrastructure-integration-bus)</span><br>
---------------------

Veja alguns [exemplos de websockets](https://socket.io/).

Em breve postarei um tutorial utilizando implementando Passwordless e Websockets.

### Referências

- [https://socket.io/](https://socket.io/)	
- [https://devcentral.f5.com/articles/html5-websockets-high-speed-infrastructure-integration-bus](https://devcentral.f5.com/articles/html5-websockets-high-speed-infrastructure-integration-bus) 
- [https://pt.slideshare.net/FabioTiriticco/websocket-wiith-scala-and-play-framework](https://pt.slideshare.net/FabioTiriticco/websocket-wiith-scala-and-play-framework)
