# Rob-tica-TBR
Campeonato de Robótica TBR
https://www.youtube.com/watch?v=KY-BdZ-YDMI 

Aqui vamos desenvolver nooso projeto
_________________________________________________
Dia 24/04/2024 - Ambientação com os dipositivos associados ao projeto do carro segue linha: Arduíno, Ponte H, Motores de 3V, Sensores infravermelho, jumpers, bateria 9V, Pilhas 1,5V.
__________________________________________________
Dia 08/05/2024 - Estudo de maneira isolada do funcionamento do sensor infravermelho, a intenção era determinar a sensibilidade prática e tempo de resposta de leitura. O sensor apresentou certa instabilidade em relação a leitura, presume-se que seja pela intensidade daluz ambiente. O sensor utilizado foi o HW-201. Não foi testado com outro sensor do mesmo tipo para determinar se a instabilidade era do hardware. 
Foi utilizado o seguinte código para o teste: 

const int pinSensorIR = A0; // Conecte o pino de saída do sensor ao pino analógico A0 do Arduino

void setup() {
Serial.begin(9600); // Inicializa a comunicação serial com baud rate de 9600 bps
}

void loop() {
// Lê a tensão do sensor infravermelho
int sensorValue = analogRead(pinSensorIR);

// Convertendo a tensão lida em distância em centímetros
float distanciaCM = (6787.0 / (sensorValue - 3.0)) - 4.0;

// Exibe a distância medida no monitor serial
Serial.print("Distancia: ");
Serial.print(distanciaCM);
Serial.println(" cm");

// Aguarda um curto período de tempo antes de fazer a próxima leitura
delay(100);
}
______________________________________________
13/05/2024 - Foi utilizado o sensor infravermelho TCRT5000 como substituto do HW201. A substituição se mostrou eficiente. O sensor  TCRT5000 é mais fácil de ser ajustado e possui maior sensibilidade eficiente, além de sofrer menos anomalias provenientes da luz ambiente.







