# DigitalElectronics2_Lab7
Session 7 Laboratory


## Link to GitHub:

Link: https://github.com/raulgoi/DigitalElectronics2_Lab7/edit/main/README.md

Raúl Gómez Ibáñez

## Table

| Push Button | PC0[A0] voltage | ADC value (calculated) | ADC value (measured) |
| ----------- | --------------- | ---------------------- | -------------------- |
| Right | 0 V | 0 |  |
| Up | 0.495 V | 101 |  |
| Down | 0.784 V | 160 |  |
| Left | 1.01 V | 206 |  |
| Select | 2 V | 409 |  |
| None | 5 V | 1023 |  |

## Code 

    ISR(ADC_vect)
    {
       uint16_t value = 0;
       char lcd_string[4] = "0000";

       value = ADC;                  // Copy ADC result to 16-bit variable
       itoa(value, lcd_string, 10);  // Convert decimal value to string

       int read_LCD_buttons() {
       
       ADC

    }
