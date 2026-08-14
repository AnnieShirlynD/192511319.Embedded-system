# Embedded Systems Lab Programs

---

## Exp No: 3 — Stepper Motor using AT89C51 using Proteus

### Program

```asm
ORG 0000H

UP: MOV P2,#09H
    ACALL DELAY
    MOV P2,#0CH
    ACALL DELAY
    MOV P2,#06H
    ACALL DELAY
    MOV P2,#03H
    ACALL DELAY
    SJMP UP

DELAY: MOV R4,#18
H1:    MOV R3,#255
H2:    DJNZ R3,H2
       DJNZ R4,H1
       RET

END
```

### Output

![Exp 3 Output](media/exp3_output.jpeg)

---

## Exp No: 4 — 7 Segment Display using AT89C51 using Proteus

### Program

```asm
ORG 000H

UP: MOV P2,#0C0H
    ACALL DELAY
    MOV P2,#0F9H
    ACALL DELAY
    MOV P2,#0A4H
    ACALL DELAY
    MOV P2,#0B0H
    ACALL DELAY
    MOV P2,#99H
    ACALL DELAY
    MOV P2,#92H
    ACALL DELAY
    MOV P2,#82H
    ACALL DELAY
    MOV P2,#0F8H
    ACALL DELAY
    MOV P2,#80H
    ACALL DELAY
    MOV P2,#90H
    ACALL DELAY

DELAY: MOV R5,#10
H1:    MOV R4,#180
H2:    MOV R3,#255
H3:    DJNZ R3,H3
       DJNZ R4,H2
       DJNZ R5,H1
       RET

END
```

### Output

![Exp 4 Output](media/exp4_output.jpeg)

---

## Exp No: 9 — Arduino Based Manual Electronic Counter using Proteus

### Program

```cpp
int x0,x1,x2,x3,x4,x5,x6,x7,x8,x9;
int delay_time = 200;

void setup() {
  // configure pin2 as an input and enable the internal pull-up resistor
  pinMode(12, INPUT_PULLUP);
  pinMode(1, OUTPUT);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop() {
  // read the pushbutton value into a variable
  int sensorVal = digitalRead(12);

  if (sensorVal == LOW) {
    x0 = true;
  }

  while (x0) {
    zero();
    sensorVal = digitalRead(12);
    if (sensorVal == LOW) {
      x1 = true;
      x0 = false;
    }
  }

  while (x1) {
    one();
    sensorVal = digitalRead(12);
    if (sensorVal == LOW) {
      x2 = true;
      x1 = false;
    }
  }

  // NOTE: the source document ends here — the remaining while-loop
  // blocks (for x2 through x9) and closing braces were not present
  // in the original file and may need to be completed.
}
```

### Output

![Exp 9 Output](media/exp9_output.png)
