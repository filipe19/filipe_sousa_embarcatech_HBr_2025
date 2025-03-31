# **Digital Galton Board**  

This project implements a digital version of a Galton Board (or Plinko), demonstrating how a series of random binary decisions leads to a **normal probability distribution**.  

## **Objective**  

Create an interactive visualization that simulates the behavior of a Galton Board using:  

- OLED Display  
- Buttons to introduce imbalances into the model  

## **Materials List**  

| Component            | Connection on BitDogLab     |  
|----------------------|---------------------------|  
| BitDogLab (RP2040)   | -                         |  
| WS2812B 5x5 Matrix   | GPIO7                     |  
| OLED Display I2C     | SDA: GPIO14 / SCL: GPIO15 |  

## **Execution**  

1. Open the project in VS Code, using an environment with support for the Raspberry Pi Pico SDK (CMake + ARM compiler).  
2. Compile the project normally (Ctrl+Shift+B in VS Code or via terminal using CMake and Make).  
3. Connect your BitDogLab via USB cable and put the Pico in boot mode (press the BOOTSEL button and connect the cable).  
4. Copy the generated `.uf2` file to the storage drive that appears (RPI-RP2).  
5. The Pico will restart automatically and begin executing the code.  
6. The histogram will be updated on the OLED display, and the simulated events will appear on the LED matrix.  

## **Logic**  

- At each step, the "ball" moves left or right with a 50% probability.  
- The total number of steps defines the depth of the triangle.  
- The final position of the "ball" is recorded in the count vector.  
- The OLED bars visually represent the frequency of each position.  

## **Files**  

- `src/main.py`: Main project code.  
- `assets/galton_led.jpg`: Simulated paths.  
- `assets/galton_hist.jpg`: Distribution histogram.  

## **Project Images**  

### **LED Matrix During Execution**  
![galton_led](./assets/galton_led.jpg)  

### **Histogram on OLED**  
![galton_hist](./assets/galton_hist.jpg)  

---  

## **License**  

This project is licensed under the [MIT License](LICENSE).