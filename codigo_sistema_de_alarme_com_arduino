#define TRIG 9
#define ECHO 10
#define BUZZER 8

bool alarmeAtivado = false;
unsigned long tempoAlarme = 0;

void setup() {
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);
  pinMode(BUZZER, OUTPUT);  
  Serial.begin(9600);
}

void loop() {
  long tempo, distancia;
  
  // Medir a distância
  digitalWrite(TRIG, LOW);
  delayMicroseconds(20);
  digitalWrite(TRIG, HIGH);
  delayMicroseconds(100);
  digitalWrite(TRIG, LOW);
  
  tempo = pulseIn(ECHO, HIGH);
  
  distancia = tempo * 0.034 / 2;
  
  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");
  
  // Ativar o alarme se a distância for menor que 15
  if (distancia > 15) {
    tone(BUZZER,10000, 500);
    delay(200);
    noTone(BUZZER);
    //alarmeAtivado = true;
    //tempoAlarme = millis();
    delay(300);
  }

  /*// Desativar o alarme após 3 segundos 
  if (alarmeAtivado && (millis() - tempoAlarme) >= 3000) {
      tone(BUZZER,2000, 500);
      alarmeAtivado = false;
  }*/
  //delay(200);
}
