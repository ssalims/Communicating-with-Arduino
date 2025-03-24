# Serial-Available
1. Communication on Serial 

/////////////////////////////////////////////////////////////////////////

//EXERCISE 1
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  
}

void loop() {
  
    if (Serial.available() > 0) { // Check if data is available
        char received = Serial.read(); // Read one character
        //received=received+1;
        Serial.print("Received: ");
        Serial.println(received);
    }
}

/////////////////////////////////////////////////////////////////////////

//EXERCISE 2
int dat1,dat2 ; //global variable
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);

}

void loop() {
  // put your main code here, to run repeatedly:
  // ask user to key in a number
  Serial.println("Please enter a number1:");
  while(!Serial.available()); // wait until user enter something
  dat1 = Serial.parseInt();
  Serial.println("Please enter a number2:");
  while(!Serial.available()); // wait until user enter something
  dat2 = Serial.parseInt();
  Serial.print(dat1);
  Serial.print(dat2);
}

/////////////////////////////////////////////////////////////////////////

//EXERCISE 3
//ASCII (American Standard Code for Information Interchange)

int incomingByte = 0; // for incoming serial data

void setup() {
  Serial.begin(9600); // opens serial port, sets data rate to 9600 bps
}

void loop() {
  // reply only when you receive data:
  if (Serial.available() > 0) {
    // read the incoming byte:
    incomingByte = Serial.read();

    // say what you got:
    Serial.print("I received: ");
    Serial.println(incomingByte, DEC);
  }
}

/////////////////////////////////////////////////////////////////////////

//EXERCISE 4
//ASCII (American Standard Code for Information Interchange)

void setup(){
    Serial.begin(9600);
}

void loop(){
    if(Serial.available()){
      int t = Serial.read();
      Serial.println(t);
      }
}

/////////////////////////////////////////////////////////////////////////

//EXERCISE 5
//STRING

void setup() {
      Serial.begin(9600);
    }

    void loop() {
      Serial.println("Enter data:");
      while (Serial.available() == 0) {}     //wait for data available
      String teststr = Serial.readString();  //read until timeout
      teststr.trim();                        // remove any \r \n whitespace at the end of the String
      if (teststr == "red") {
        Serial.println("A primary color");
      } else {
        Serial.println("Something else");
      }
    }


