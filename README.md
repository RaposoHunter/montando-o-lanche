# Projeto Montando o Lanche

Este projeto foi desenvolvido como parte da seção 2 do curso [Desenvolvimento Web Avançado com Vue (v2 e v3) e Vuex](https://www.udemy.com/course/desenvolvimento-web-avancado-com-vue-strapi-vuex-e-vuetify/).

## Etapa 1: Montagem

O usuário deve selecionar uma gama de opções como:

* Tipo de Pão (Gergelim ou Australiano)
* Saladas (Alface)
* Molhos (Ketchup e/ou Mostarda e/ou Maionese)
* Tipos de Hambúrguer (Bovino, Frango ou Soja)

Ao selecionar as opções será exibido um *preview* do lanche atual à esquerda para permitir que o usuário visualize como o lanche será montado. 

<small>Imagens meramente ilustrativas</small>

## Etapa 2: Dados do usuário

O usuário deve informar o seu nome e endereço para confirmar o pedido.

## Etapa 3: Repetir/Novo pedido

Nesta etapa o usuário é notificado que o pedido está sendo preparado e será entregue em até 10 minutos. Ainda nesta etapa o usuário pode refazer o pedido, alterando qualquer opção necessária, ou fazer um pedido completamente novo.

Caso nenhuma opção seja escolhida dentro de um intervalo de 7 segundos, o sistema redirecionará o usuário automaticamente para a etapa 1.