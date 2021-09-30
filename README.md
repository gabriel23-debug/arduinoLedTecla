# arduinoLedTecla
O led acende apertando determinada tecla e apaga apertando outra. 

#define ledpin 10
char byteLido = ' ';

void setup() {

Serial.begin(9600);
pinMode(ledpin, OUTPUT);

}

void loop() {

Serial.println("Comandos de led");
Serial.println("Informar número de repetição");
Serial.println("1 a 5, 0 - cancela.");
while (Serial.available() <= 0) {}
byteLido = Serial.read();

if (byteLido == '0') {
digitalWrite(ledpin, LOW);
Serial.println("_______________________");
Serial.println("_________LED Desativado"); 
Serial.println("_______________________");
 } else if (byteLido == '1') {
digitalWrite(ledpin, HIGH);
Serial.println("_______________________");
Serial.println("____________LED Ativado"); 
Serial.println("_______________________");
 } else {
Serial.println("_______________________");
Serial.println("_______Comando inválido"); 
Serial.println("_______________________");
 }

Serial.println("");



}
