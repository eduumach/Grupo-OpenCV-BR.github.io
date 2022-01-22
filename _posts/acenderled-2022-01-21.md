---
layout: post
title:  ""
date:   2020-12-04 08:25:34 -0300
categories: canny bordas
---

# Acendendo led com a mão

Esse é um projeto de apresentação, bem simples. Com esse projeto você vai acender um led se sentindo o tony stark hahaha.

<iframe src="https://giphy.com/embed/t1lmQR7sXeZJC" width="480" height="284" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/iron-man-fabulous-robert-downey-jr-t1lmQR7sXeZJC"></a></p>

# O que vamos precisar?

* Arduino.
* IDE ou editor de código que goste.
* Python e pip instalado
* Vontade de aprender

# Vamos começar

## Arduino

### Diagrama

Primeiro vamos montar nossa arduino, são poucas ligações seque o diagram:

![Diagrama](https://files.catbox.moe/j7gcrn.png)

### Código

Opaa, chegamos na parte legal os códigos hehehe, não vou me aprofundar muito em arduino por que esse não é o objetivo do tutorial, mas vou explicar como o código funciona.

```C++
void setup() {
  pinMode(12, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  
  if(Serial.available()){

    char ser = Serial.read();

    if(ser == 'a'){
      digitalWrite(12, LOW);
    }else if(ser == 'b'){
       digitalWrite(12, HIGH);
    }
  }
}
```

 Nessa linha estamos criando a preparação do arduino, o código que vai ser executado apenas uma vez:

```C++
void setup() {
```

Agora esta linha estamos colocando o pino 12 como OUTPUT (saída)

```C++
 pinMode(12, OUTPUT);
```

Agora vamos configurar a velocidade de comunicação da nossa porta serial (importante lembrar ela, pois é ela que vai fazer a comunicação do arduino com nosso código).

```C++
 Serial.begin(9600);
```

Agora vamos inciar o loop do arduino, o código daqui para baixo vai ficar executando o tempo todo.

```C++
void loop() {
```

Agora toda vez que o loop começar novamente vamos verificar sem tem algo no serial.

```C++
  if(Serial.available()){
```

Vamos ler o que chegou no serial e salvar em um carácter chamado "ser".

```C++
    char ser = Serial.read();
```

Agora é um if simples, se o carácter for "a" faça isso (que é mandar energia para o pino 12):

```C++
      digitalWrite(12, LOW);
```

E se não, faça isso(que é desativar a energia do pino 12):

```C++
       digitalWrite(12, HIGH);
```
