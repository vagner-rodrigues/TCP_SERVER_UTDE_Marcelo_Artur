
# TCP Server UTDE(Umidade, Temperatura, Distancia, Estado)


O aplicativo cria um socket TCP com o número de porta especificado e aguarda uma solicitação de conexão do cliente. Depois de aceitar uma solicitação do cliente, a conexão entre o servidor e o cliente é estabelecida e o aplicativo aguarda que alguns dados sejam recebidos do cliente. Os dados recebidos são processados como texto ASCII e retorna a resposta ao cliente cuja oque foi solicitado.

## Antes de começar

### Verifique a versão do seu SDK.
- [X] Algoritmo Desenvolvido com SDK Version ESP-IDF v4.1-dirty
### Baixe o App completo.
- [X] https://github.com/Marcelo-C0D3/TCP_SERVER_UTDE_Marcelo_Artur
### Descompacte-o na pasta do seu SDK.
- [X] Libs DHT e Ultrasonic. já incluidos e importados neste diretorio.

### Requisitos de Hardware

```
* Este exemplo pode ser executado em qualquer placa de desenvolvimento ESP32 comumente disponível.
* Necessario sensor DHT11(Defina os pinos no cabeçario do projeto/main.c)Default(GPIO_NUM_0).
* Necessario sensor HC-SR04(Defina os pinos no cabeçario do projeto/main.c)Default(GPIO_NUM_2/GPIO_NUM_13).
* Necessario LED(Defina os pinos no cabeçario do projeto/main.c) Default(`GPIO_NUM_14`).
```

### Configure o Projeto

* Navegue até a pasta do projeto, com seu console do SDK (ESP-IDF Command Prompt) .
```
idf.py menuconfig
```
#### Após rodar o comando a seguinte tela deve aparecer:

![menuconfig](https://user-images.githubusercontent.com/56330822/99081292-5884e980-25a1-11eb-9a85-5e683d7ec984.PNG)

#### Acesse `Example Configuration` .

![port](https://user-images.githubusercontent.com/56330822/99081795-190acd00-25a2-11eb-8f07-d66c372a836d.PNG)

#### Configure a Porta `Port`, se quiser. Por padrão está executando a porta 3333.
#### Retorne a tela anterior.

#### Acesse `Example Connection Configuration` .

![Redeconfig](https://user-images.githubusercontent.com/56330822/99082473-f4fbbb80-25a2-11eb-8547-e671b19ec0ef.PNG)

#### Configure o Nome de sua rede `WiFi SSID`. Necessario para executar o servidor.
#### Configure A Senha da sua rede `WiFi Password`. Necessario para executar o servidor.
#### Desmarque a caixa `Obtain IPv6 link-local address`. Vem selecionada por padrão, e desnecessario para uso em redes IPv4.
#### Apos os procedimentos. Salve as alteraçoes e Saia do menuconfig..


### Build and Flash

Ainda na pasta do projeto, com seu console do SDK (ESP-IDF Command Prompt) 
Construa o projeto e envie-o para a placa, em seguida, execute a ferramenta de monitoramento para visualizar a saída serial:

```
idf.py -p PORT flash monitor
```

#### Após rodar o comando a seguinte tela deve aparecer:

![rodando](https://user-images.githubusercontent.com/56330822/99083292-190bcc80-25a4-11eb-8d32-2093400483a2.PNG)

## Otimo! O servidor está no Ar.

#### Em vermelho na imagem, visualize o `IP` que o servidor obteve e em sequencia a `Porta` que definimos. Observe no seu console os dados atribuidos, e os guarde, que iremos utilizar em breve.

### Estabelecer uma conxão Cliente/Servidor.

#### Neste exemplo eu uso o Realterm, para estabelecer uma conexão cliente/server.
Lembrando inicie primeiro o servidor para receber os dados solicitados pelo cliente (aplicativo).

### Após baixar e instalar o realterm em seu dispositivo, execute-o.
### Vá até a Aba `Port`. Mostrada na iamgem.

![realterm1](https://user-images.githubusercontent.com/56330822/99087159-355e3800-25a9-11eb-9d7c-0d2e6e77b8c4.PNG)

### Na Aba Port. Prencha o campo `Port` com `IP:PORT` obtidos anteriormente. Apos isto Click! em Change para aplicar as configuraçoes.
### Ao lado, em Status os seguintes campos devem aparecer como vizualizados na imagem.

## Pronto! A conexão Cliente/Server foi estabelecia.

### Agora voce pode enviar seus codigos ASCII ao servidor. E receber as informaçoes requisitadas.
### Exemplo de codigo `TEMP` e `DIST` enviados. Mostrados na imagem.

![req](https://user-images.githubusercontent.com/56330822/99088037-3cd21100-25aa-11eb-85b8-7390de8bc8fe.PNG)

### Agora voce mesmo pode enviar os codigos: `TEMP`, `DIST`, `UMID`, `LEDB` e `HELP` para obter respostas do servidor.

## Hardware montado

![1605657509003](https://user-images.githubusercontent.com/56330822/99466001-52349b80-291a-11eb-998a-e4559d3dead5.jpg)
![1605657508995](https://user-images.githubusercontent.com/56330822/99466040-68daf280-291a-11eb-879b-badacaad7450.jpg)

### Funcionamento(links abaixo).

https://drive.google.com/file/d/1FW2UvrYbyrKgUVBmfQuviJEhruBpIOhX/view?usp=sharing
https://drive.google.com/file/d/1FV6pgn5strIO8e3OTrx3VouHx9_sFR5Q/view?usp=sharing
