# DIY-Arduino-Based-Gas-Alert-System

**Description:**

This Arduino code implements a basic gas detector circuit. The system uses an analog sensor to detect the presence of gas and alerts through visual and auditory signals. Additionally, it provides appropriate status messages through the serial monitor.


**Hardware:**

* Arduino Uno or compatible board
* MQ-x gas sensor (specific model depends on gas type)
* 10kΩ resistor (for the gas sensor)
* 220Ω resistor (for the LED) (optional, use higher value for lower brightness)
* Red LED (connected to pin 2)
* Green LED (connected to pin 3)
* Buzzer (connected to pin 4)

## Configuration
- `Input`: Analog input from the gas sensor
- `R_LED`: Digital output to control the Red LED
- `G_LED`: Digital output to control the Green LED
- `Buzzer`: Digital output to control the buzzer
- `val`: Variable to store the sensor reading
- `MAX`: Threshold value for gas detection

**Software:**

* Arduino IDE ([https://support.arduino.cc/hc/en-us/articles/360019833020-Download-and-install-Arduino-IDE](https://support.arduino.cc/hc/en-us/articles/360019833020-Download-and-install-Arduino-IDE))

**Wiring:**

1. Connect the MQ-x gas sensor according to its datasheet. Typically, VCC connects to 5V, GND to ground, and output (often labeled "S" or "OUT") connects to the Arduino's A0 pin through a 10kΩ resistor.
2. Connect the anode (longer leg) of the red LED to pin 2 through a 220Ω resistor (optional). Connect the cathode (shorter leg) to ground.
3. Connect the anode of the green LED to pin 3 through a 220Ω resistor (optional). Connect the cathode to ground.
4. Connect the positive leg of the buzzer to pin 4 and the negative leg to ground.

**Usage:**

1. Upload the code to your Arduino board.
2. Open the Arduino serial monitor (Tools -> Serial Monitor) at 9600 baud.
3. The program will continuously monitor the gas sensor reading. 
   * If the gas concentration exceeds the threshold (defined by the `MAX` variable), the red LED will turn on, the buzzer will sound, and "GAS LEAKING" will be displayed in the serial monitor.
   * Otherwise, the green LED will be on, and "NORMAL" will be displayed, indicating no gas detected.

**Notes:**

* This is a basic example. The gas sensor threshold (`MAX`) may need to be adjusted based on the specific sensor model and desired sensitivity. 
*  For improved accuracy, consider averaging multiple sensor readings in the `loop` function.

## Safety Warning
Always ensure proper ventilation when testing this system and never expose it to flammable gases without proper safety measures in place.
