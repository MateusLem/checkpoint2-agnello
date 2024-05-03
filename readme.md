# Checkpoint 2 - Vinheria Agnello

## Bibliotecas Necessárias
Antes de executar o código, certifique-se de ter baixado as seguintes bibliotecas:

```
#include <LiquidCrystal.h>
#include <DHT.h>
```

## Descrição do Projeto
Este projeto visa auxiliar a Vinheria Agnello no controle de qualidade de seus produtos. Utilizando sensores e um Arduino UNO, o sistema oferece avisos visuais e sonoros, garantindo maior segurança em relação à qualidade dos produtos.

## Segmentação do Código

### Configurações Iniciais
O código começa com a definição dos pinos e bibliotecas necessárias, além da inicialização de componentes como o LCD e o sensor DHT.

```
//Imports
#include <LiquidCrystal.h>
#include <DHT.h>

#define DHTPIN 9 // Pino do DHT
#define DHTTYPE DHT11  // Tipo de sensor DHT

DHT dht(DHTPIN, DHTTYPE); // DHT

LiquidCrystal lcd(12, 11, 10, 5, 4, 3, 2); // Pinos do display LCD
```

### Funções Principais
O loop principal do programa executa uma série de verificações e ações com base nas leituras dos sensores, incluindo a exibição de dados no LCD, controle de LEDs e acionamento do buzzer.


```
void loop() {
  int valorLDR = analogRead(pinLDR); 
  lightLevel = map(valorLDR, 500, 969, 0, 100); //Utiliza a função map para interpretar os valores do LDR

  float temp = dht.readTemperature(); // Lê a temperatura do sensor DHT
  float humid = dht.readHumidity();   // Lê a umidade do sensor DHT

  verifyLDR(); // Verifica o nível de luz

  // Outras verificações e ações...
}
```

### Animações no LCD
Há funções dedicadas à exibição de animações no LCD, como a animação do "Pac-Man" e um slogan da empresa.

```
// Animação do "Pac-Man" comendo a logo da empresa no LCD
void move_pac() {
  // Código da animação...
}

// Animação de letras caindo para o slogan
void slogan() {
  // Código da animação...
}
```

### Exibição de Dados
Outras funções são responsáveis por calcular médias de leituras dos sensores e exibir informações no LCD de acordo com essas médias.

```
// Calcula a média das últimas 10 leituras e exibe as telas de cada campo
void tenthRead() {
  // Cálculo da média...
}

// Exibe dados no LCD
void show_data() {
  // Exibição dos dados...
}
```

### Verificação de Nível de Luz
Uma função específica verifica o nível de luz ambiente e controla o comportamento dos LEDs e do buzzer com base nessa informação.

```
// Verifica o nível de luz do ambiente
void verifyLDR() {
  // Verificação do nível de luz...
}
```

## Simulador Wokwi
Para visualizar o projeto em execução, você pode acessar o simulador Wokwi [aqui](https://wokwi.com/projects/396351769363094529). Este simulador utiliza um modelo diferente de sensor DHT e de foto resistor.

## Inicialização do Projeto

### Lista de Peças
- 1x Arduino UNO3
- 1x Sensor DHT11
- 1x Fotoresistor
- 3x LEDs (vermelho, amarelo e verde)
- 1x Buzzer Piezo
- 1x Tela LCD 16x2 (Modelo tradicional)
- 4x Resistores de 1k Ohm
- 1x Potenciômetro

### Montagem do Arduino
1. Conecte o sensor DHT11 ao pino 9 do Arduino.
2. Conecte o LCD aos pinos 12, 11, 10, 5, 4, 3 e 2 do Arduino.
3. Conecte os LEDs aos pinos 8 (vermelho), 7 (amarelo) e 6 (verde) do Arduino.
4. Conecte o fotoresistor ao pino analógico A0 do Arduino.
5. Conecte o buz

zer ao pino digital 13 do Arduino.
6. Utilize resistores de 1k Ohm para limitar a corrente dos LEDs.
7. Ajuste o potenciômetro conforme necessário para o contraste do LCD.

## Colaboradores do Projeto
<div style="display: flex; justify-content: space-between; align-items: center;">
<a href="https://github.com/AnaTorresLoureiro" target="_blank" style="text-align: center; margin-right: 10px;">
<img loading="lazy" src="https://avatars.githubusercontent.com/AnaTorresLoureiro" width=120>
<p style="font-size:min(2vh, 36px); margin-top: 10px;">Ana Laura Torres Loureiro - RM 554375</p>
</a>
<a href="https://github.com/MuriloCngp" target="_blank" style="text-align: center; margin-right: 10px;">
<img loading="lazy" src="https://avatars.githubusercontent.com/MuriloCngp" width=120>
<p style="font-size:min(2vh, 36px); margin-top: 10px;">Murilo Cordeiro Ferreira - RM 556727</p>
</a>
<a href="https://github.com/MateusLem" target="_blank" style="text-align: center; margin-right: 10px;">
<img loading="lazy" src="https://avatars.githubusercontent.com/MateusLem" width=120>
<p style="font-size:min(2vh, 36px); margin-top: 10px;">Mateus da Costa Leme - RM 557803</p>
</a>
<a href="https://github.com/Geronimo-augusto" target="_blank" style="text-align: center; margin-right: 10px;">
<img loading="lazy" src="https://avatars.githubusercontent.com/Geronimo-augusto" width=120>
<p style="font-size:min(2vh, 36px); margin-top: 10px;">	Geronimo Augusto Nascimento Santos - RM 557170</p>
</a>
<a href="https://github.com/Vitorr-AF" target="_blank" style="text-align: center; margin-right: 10px;">
<img loading="lazy" src="https://avatars.githubusercontent.com/Vitorr-AF" width=120>
<p style="font-size:min(2vh, 36px); margin-top: 10px;">Vitor Augusto França de Oliveira - RM 555469</p>
</a>
</div>

