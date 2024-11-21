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


## Descrição do projeto - Global Solution
<p>Este projeto implementa um sistema de monitoramento da qualidade do ar, projetado para ser utilizado em filtros de poluentes ou ambientes abertos. O dispositivo mede temperatura, umidade e fluxo de gás e calcula a saturação do ar com base nesses valores. As informações são publicadas em um broker MQTT, facilitando sua integração com sistemas de Internet das Coisas (IoT).</p>

<p><b>Objetivo do projeto:</b> O objetivo é desenvolver um sistema que monitore variáveis relacionadas à qualidade do ar, como:</p>
<ul>
  <li>Temperatura e umidade através de um sensor DHT22.</li>
  <li>Fluxo de gás utilizando um potenciômetro (simulação).</li>
  <li>Saturação do ar, calculada com base nos valores obtidos de temperatura e umidade.</li>
</ul>
Os dados coletados são enviados em tempo real para um broker MQTT, permitindo que sejam utilizados em análises ou sistemas de controle de poluentes.

<p><b>Funcionalidades:</b></p>
<ul>
  <li>- Medição de temperatura e umidade com um sensor DHT22.</li>
  <li>- Simulação de fluxo de gás com um potenciômetro.</li>
  <li>- Cálculo da saturação do ar com base na fórmula: saturação = umidade x (temperatura/TEMP_MAX) onde TEMP_MAX é a temperatura máxima teórica ajustável</li>
  <li>- Publicação dos dados em formato JSON no broker MQTT.</li>
  <li>- Reconexão automática ao Wi-Fi e MQTT em caso de falhas.</li>
  <li>- Sistema extensível para inclusão de novos sensores ou funcionalidades.</li>
</ul>


<p><b>Configuração do Hardware:</b></p>
<p>Esquema de Conexão:</p>
DHT22:
<ul>
  <li>VCC: 3.3V do ESP32</li>
  <li>GND: GND do ESP32</li>
  <li> Data: GPIO 12</li>
</ul>
Potenciômetro:
<ul>
  <li>VCC: 3.3V do ESP32</li>
  <li>GND: GND do ESP32</li>
  <li>Sinal: GPIO 34</li>
</ul>

<p><b>Configuração do Software:</b></p>
<ul>
  <li> Instale a Arduino IDE no seu computador.</li>
  <li> Configure a placa ESP32 na IDE: Acesse Ferramentas > Placa > Gerenciador de Placas.
 Instale a plataforma ESP32.
 Selecione a placa ESP32 e a porta correspondente.</li>
  <li> Instale as bibliotecas necessárias: Acesse Ferramentas > Gerenciador de Bibliotecas e procure por:
PubSubClient
DHT sensor library for ESPx (DHTesp)
ArduinoJson</li>
  <li> Atualize as credenciais no código: const char *SSID = "SEU_WIFI";
const char *PASSWORD = "SUA_SENHA";
</li>
</ul>

<p><b>Como usar:</b></p>
<ul>  
  <li>1. Faça o upload do código para o ESP32 através da Arduino IDE.</li>
  <li>2. Conecte o ESP32 à alimentação.</li>
  <li>3. Acompanhe o monitor serial para verificar o status das conexões e os dados publicados: Baud rate: 115200.</li>
  <li>4.Utilize um cliente MQTT (ex.: MQTT Explorer) para visualizar os dados no tópico configurado:</li>
</ul>

<p><b>Dependências:</b> </p>

