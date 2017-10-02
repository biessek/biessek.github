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
---

> 70% dos usuários esquecem sua senha uma vez por mês e, em média, tentam 2.4 senhas antes de acertar
> \- Regina Dugan | Google SVP

Os usários são normalmente esquecidos ou descuidados(ou ambos rs) com senhas, isso qualquer programador reconhece, então porque não mudar?  
  
Uma das primeiras aplicações a utilizar esta técnica é o *Whatsapp*, que implementa o registro via notificação SMS e login via Token( Na versão web, utilizando QrCode).

![Whatsapp Registration](https://www.whatsapp.com/img/faq/pt_br/android/16913175578913.png)
{:.imgreg style="width: 200px"}

### É esta a proposta da autenticação Passwordless, que promete alguns **benefícios**:    
<br>
-  **Mais fácil para os usuários.** - Não precisam se preocupar em lembrar de uma senha complicada com caracteres alfanuméricos e símbolos.  
  

-  **Mais seguro.** - Geralmente o usuário repete a senha em diferentes sites(quem nunca?). Os tokens são válidos por um período de tempo, é como se o usuário tivesse uma nova senha a cada sessão. Muito mais difícil de sofrer um ataque de força bruta.  
  
-  **Flexível.** - A forma como o token é enviado ao usuário é dinâmica, SMS, email, QrCode, fica a critério do desenvolvedor. 
  
No **Auth0** há uma série de tutoriais para quem deseja testar: [Auth0 Passwordless](https://auth0.com/docs/connections/passwordless)

Além disso o Facebook lançou recentemente o [Account Kit](https://developers.facebook.com/docs/accountkit/?locale=pt_BR) para quem deseja utilizar o login por SMS.


Referências:   
[https://passwordless.net](https://passwordless.net)  
[https://auth0.com/passwordless](https://auth0.com/passwordless)  