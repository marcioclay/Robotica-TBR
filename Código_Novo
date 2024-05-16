const int motorA = 5; //velocidade motor A - de 0 a 255
const int motorB = 6; //velocidade motor B - de 0 a 255
const int dirA = 7; //direcao do motor A - HIGH ou LOW
const int dirB = 8; //direcao do motor B - HIGH ou LOW  
int Sensor1 = 5;
int Valor_Sensor1 = 0; 
int Sensor2 = 6; 
int Valor_Sensor2 = 0;

void setup(){
  pinMode(motorA, OUTPUT);
  pinMode(motorB, OUTPUT);
  pinMode(dirA, OUTPUT);
  pinMode(dirB, OUTPUT);
  digitalWrite(dirA, HIGH); 
  digitalWrite(dirB, HIGH);
  
  // Inicia a comunicação serial com uma taxa de 9600 baud
  Serial.begin(9600);
  
  // Desliga os sensores
  pinMode(Sensor1, INPUT);
  pinMode(Sensor2, INPUT);
}

void loop(){
  Valor_Sensor1 = analogRead(Sensor1); 
  Valor_Sensor2 = analogRead(Sensor2); 
  
  if((Valor_Sensor1 > 700) && (Valor_Sensor2 > 700)){
    analogWrite(motorA, 150); 
    analogWrite(motorB, 150);
  }
  
  if((Valor_Sensor1 < 700) && (Valor_Sensor2 > 700)){
    analogWrite(motorA, 0); 
    analogWrite(motorB, 200);
  }
  
  if((Valor_Sensor1 > 700) && (Valor_Sensor2 < 700)){
    analogWrite(motorA, 200); 
    analogWrite(motorB, 0);
  }
  
  // Envia os valores dos sensores para o monitor serial
  Serial.print("Sensor1: ");
  Serial.print(Valor_Sensor1);
  Serial.print("\t Sensor2: ");
  Serial.println(Valor_Sensor2);
  
  delay(100); // Pequeno atraso para não sobrecarregar o monitor serial
}
