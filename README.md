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
       
       // Funtion for read the button with the analog value
       
       ADC = AnalogRead(0);
       int k = (AnalogRead(0) - ADC);
       if (5 < abs(k)) return btnNONE;
       if (ADC > 1000) return btnNONE;
       if (ADC < 50)   return btnRIGHT;  
       if (ADC < 110)  return btnUP; 
       if (ADC < 190)  return btnDOWN; 
       if (ADC < 220)  return btnLEFT; 
       if (ADC < 500)  return btnSELECT;   
       return btnNONE;
       
     }
     
     lcd_gotoxy(1, 0);
     
     
       switch (ADC)               // depending on which button was pushed, we perform an action
     {
       case btnRIGHT:
     {
       lcd_puts("RIGHT ");
       break;
     }
       case btnLEFT:
     {
       lcd_puts("LEFT   ");
       break;
     }
       case btnUP:
     {
       lcd_puts("UP    ");
       break;
     }
       case btnDOWN:
     {
       lcd_puts("DOWN  ");
       break;
     }
       case btnSELECT:
     {
       lcd_puts("SELECT");
       break;
     }
       case btnNONE:
     {
       lcd_puts("NONE  ");
       break;
     }
     
         }
         
         

## UART communication

### Hand_Drawn 


![UART](https://user-images.githubusercontent.com/91128806/140773129-90371a1b-0f13-4202-9671-ca52a921298d.jpeg)



### Flowchart
