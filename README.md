Smoke Detector using Gas Sensor using arduino
A Smoke Detector using a Gas Sensor for Arduino is a prime example of a project that assures beginners and hobbyists in learning how to develop a safety device. 
With this gas sensor, the presence of smoke or harmful gases in the air can be easily detected.
Data coming from the sensor is processed on the Arduino board, which sounds an alarm or takes some other action upon detection of smoke. 
This project will teach you about sensors, data processing, and safety applications. It really is a hands-on way to learn electronics and programming while building a useful gadget. 
Get your Arduino board and gas sensor to start creating your smoke detector today

 Write a code for Smoke Detector using Gas Sensor using arduino

 int red_LED_PIN = 11;
 
int green_LED_PIN = 9;

int blue_LED_PIN =  10;

int buzzer = 6;

int smoke_detector = A0;

int safety_lim = 60;


void setup() {

  pinMode(red_LED_PIN, OUTPUT);
  
  pinMode(green_LED_PIN, OUTPUT);
  
  pinMode(blue_LED_PIN, OUTPUT);
  
  pinMode(buzzer,  OUTPUT);
  
  pinMode(smoke_detector, INPUT);
  
  Serial.begin(9600); 
  
}

void  loop() {

  int sensor_read = analogRead(smoke_detector); 
  

  Serial.print("Smoke  Density: ");
  
  Serial.println(sensor_read);
  
  
  if (sensor_read > safety_lim)
  
   
  {
  
	analogWrite(red_LED_PIN,255);
 
    analogWrite(green_LED_PIN, 0);
    
    tone(buzzer,500, 100); 
    
  }
  
  else
  
  {
  
    analogWrite(green_LED_PIN, 255);
    
    analogWrite(red_LED_PIN,0);
    
    noTone(buzzer); 
    
  }
  
  delay(50);
  
}
