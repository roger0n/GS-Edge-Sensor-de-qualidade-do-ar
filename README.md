# Sensor monitora a qualidade do ar
## Turma: 1ESA - FIAP

## integrantes
### AUGUSTO FERREIRA ROGEL DE SOUZA (RM 557709)
### JUAN FRANCISCO ALVES MURADAS (RM 555541)
### AHMAD JAAFAR (RM 97927)
#
### Componentes 
- 1 ESP32 [https://docs.wokwi.com/pt-BR/guides/esp32]
- 1 DHT22 [https://docs.wokwi.com/pt-BR/parts/wokwi-dht22]
- 1 POTENCIOMETRO [https://docs.wokwi.com/pt-BR/parts/wokwi-potentiometer]
- 1 Breadboard
- 6 Jumpers
### Bibliotecas Utilizadas
- WiFi (inclusa na IDE)
- DHTesp
- PubSubClient
- ArduinoJson


### Descrição do projeto - Global Solution
<p>Este projeto implementa um sistema de monitoramento da qualidade do ar, projetado para ser utilizado em filtros de poluentes ou ambientes abertos. O dispositivo mede temperatura, umidade e fluxo de gás e calcula a saturação do ar com base nesses valores. As informações são publicadas em um broker MQTT, facilitando sua integração com sistemas de Internet das Coisas (IoT).</p>

<p><b>Objetivo do projeto:</b> O objetivo é desenvolver um sistema que monitore variáveis relacionadas à qualidade do ar, como:</p>

Temperatura e umidade através de um sensor DHT22.
Fluxo de gás utilizando um potenciômetro (simulação).
Saturação do ar, calculada com base nos valores obtidos de temperatura e umidade.
Os dados coletados são enviados em tempo real para um broker MQTT, permitindo que sejam utilizados em análises ou sistemas de controle de poluentes.



<p><b>Funcionalidades:</b></p>
- Medição de temperatura e umidade com um sensor DHT22.
- Simulação de fluxo de gás com um potenciômetro.
- Cálculo da saturação do ar com base na fórmula: saturação = umidade x (temperatura/TEMP_MAX) onde TEMP_MAX é a temperatura máxima teórica ajustável
- Publicação dos dados em formato JSON no broker MQTT.
- Reconexão automática ao Wi-Fi e MQTT em caso de falhas.
- Sistema extensível para inclusão de novos sensores ou funcionalidades.

<p><b>Como usar:</b></p>
1. Faça o upload do código para o ESP32 através da Arduino IDE.

2. Conecte o ESP32 à alimentação.

3. Acompanhe o monitor serial para verificar o status das conexões e os dados publicados: Baud rate: 115200.

4.Utilize um cliente MQTT (ex.: MQTT Explorer) para visualizar os dados no tópico configurado:

<p><b>Dependências:</b> </p>

<p><b>O codigo:</b> </p>



<p><b>Conclusão:</b> </p>
