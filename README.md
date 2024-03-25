# Arduino-LineSensor

# 1번코드

```arduino
#define ledPin 13 //LED는 디지털 핀 13에 열결됨
#define inPin 7   //pushbutton은 디지털 핀 7에 연결됨
int val = 0;   // 읽은 값을 지정할 변수 

void setup() {
  pinMode(ledPin, OUTPUT); //디지털 핀 13을 출력으로 설정
  pinMode(inPin, INPUT);  //디지털 7을 입력으로 설정 
  Serial.begin(9600);  
}

void loop() {
  val = digitalRead(inPin);  // 입력 핀으로부터 읽기, 7번 핀에서 VOC 연결 또는 GND 연결

  Serial.print("input data ");
  Serial.println(val);
  digitalWrite(ledPin, val); //LED를 버튼 값으로 설정
}
```

# 2번코드

```python
#define ledPin 13 //LED는 디지털 핀 13에 열결됨
int linesensor_data[5] = {0,0,0,0,0};
int linesensor_pin[5] = {2, 3, 4, 5, 6};


void setup() {
  int i;
  pinMode(ledPin, OUTPUT); //디지털 핀 13을 출력으로 설정
  for (i=0;i<5;i++);
  {
    pinMod(linesensor_pin[1], INPUT);
  }
  Serial.begin(9600);  
}

void loop() {
  int i;
  for(i=0;i<5;i++)
  {
    linesensor_data[i] = digitalRead(linesensor_pin[1]);
  }
  Serial.print("Input data ");
  for(i=0;i<5;i++)
  {
    Serial.print(linesensor_data[1]);
    Serial.print("  ");
  }
  Serial.print("  ")
}
```
