[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/nTFtQnuC)

# Pedro Ivo Santana Melo - 202004776

## Temperatura (MQTT In)
* O nó MQTT In no Node-RED é usado para receber mensagens MQTT em um fluxo. Ele é configurado para escutar um tópico MQTT específico e encaminhar as mensagens recebidas para outros nós no fluxo para processamento.

## Verificar_temperatura (Function)
* Este nó executa um código em JavaScript, que recebe a temperatura do tópico e verifica se ele representa um estado febril ou não. Se o valor for maior ou igual a 38, ele modifica o payload para “temperatura_febril” e se for menor, ele modifica para “temperatura_normal”.

## Modify-payload (Function)
* Este nó executa um código JavaScript, que adiciona a data e a hora da publicação no payload. Ou seja, o payload passa a ter o momento da publicação junto com a temperatura e o estado da pessoa.

## Temp/log_temperatura (Write File)
* Este nó é usado para escrever os dados em um arquivo no sistema de arquivos local. Ele permite especificar o caminho do arquivo e o conteúdo a ser escrito, permitindo o armazenamento das informações de forma persistente, nesse caso o registro de logs.

## Alerta_febre (MQTT Out)
* Este nó é usado para enviar as publicações no tópico MQTT, permitindo o monitoramento das temperaturas de uma pessoa ao longo do tempo.

