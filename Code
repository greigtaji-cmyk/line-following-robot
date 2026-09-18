#define in1 9
#define in2 8
#define in3 7
#define in4 6
#define enA 10
#define enB 5

#define LEFT_SENSOR A0 // Left sensor pin
#define RIGHT_SENSOR A1 // Right sensor pin

int M1_Speed = 80; // speed of motor 1
int M2_Speed = 80; // speed of motor 2
int LeftRotationSpeed = 250;  // Left Rotation Speed
int RightRotationSpeed = 250; // Right Rotation Speed

void setup() {
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);

  pinMode(enA, OUTPUT);
  pinMode(enB, OUTPUT);

  pinMode(LEFT_SENSOR, INPUT); // Left sensor as input
  pinMode(RIGHT_SENSOR, INPUT); // Right sensor as input
}

void loop() {
  int LEFT_SENSOR_STATE = digitalRead(LEFT_SENSOR);
  int RIGHT_SENSOR_STATE = digitalRead(RIGHT_SENSOR);

  // Maze Solving Logic

  // 1. If both sensors detect the line, move forward.
  if (LEFT_SENSOR_STATE == 0 && RIGHT_SENSOR_STATE == 0) {
    forward();
  }
  // 2. If the left sensor detects the line (left curve), turn left.
  else if (LEFT_SENSOR_STATE == 0 && RIGHT_SENSOR_STATE == 1) {
    left();
  }
  // 3. If the right sensor detects the line (right curve), turn right.
  else if (LEFT_SENSOR_STATE == 1 && RIGHT_SENSOR_STATE == 0) {
    right();
  }
  // 4. If both sensors are off the line, stop (dead-end or lost the line).
  else if (LEFT_SENSOR_STATE == 1 && RIGHT_SENSOR_STATE == 1) {
    Stop();
  }
}

void forward() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);

  analogWrite(enA, LeftRotationSpeed);
  analogWrite(enB, RightRotationSpeed);
}

void right() {
  digitalWrite(in1, HIGH);
  digitalWrite(in2, LOW);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, LOW);

  analogWrite(enA, LeftRotationSpeed);
  analogWrite(enB, RightRotationSpeed);
}

void left() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, LOW);
  digitalWrite(in4, HIGH);

  analogWrite(enA, LeftRotationSpeed);
  analogWrite(enB, RightRotationSpeed);
}

void Stop() {
  digitalWrite(in1, LOW);
  digitalWrite(in2, LOW);
  digitalWrite(in3, LOW);
  digitalWrite(in4, LOW);
}
