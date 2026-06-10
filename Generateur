#include <Stepper.h>
#include <Servo.h>

const int buttonPin = 4;  // the number of the pushbutton pin
const int ledPin = 6;    // the number of the LED pin

// variables will change:
int buttonState = 0;  // variable for reading the pushbutton status
const int stepsPerRevolution = 32*64;  // change this to fit the number of steps per revolution
// for your motor
boolean EtatBouton = LOW;
// initialize the stepper library on pins 9 through 12:
Stepper myStepper(stepsPerRevolution, 10, 12, 11,9);
Servo myservo;



void setup() {
  
   pinMode(ledPin, OUTPUT);
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT); // put your setup code here, to run once:
myStepper.setSpeed(8);
myservo.attach(5);
}

void loop() {
    // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed. If it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    // turn LED on:
    digitalWrite(ledPin, HIGH);
    myservo.write(90);
     if (EtatBouton==LOW) {
      myStepper.step(stepsPerRevolution);           
    }
    EtatBouton=HIGH;
  } else {
    // turn LED off:
    digitalWrite(ledPin, LOW);
    myservo.write(0);
    if (EtatBouton==HIGH) {

      myStepper.step(-stepsPerRevolution);
    }
    EtatBouton=LOW;    
  }// put your main code here, to run repeatedly:

}
