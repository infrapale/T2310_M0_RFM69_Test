# T2310_M0_RFM69_Test

Test code for the Adafruit M0 RFM69 Feather board

https://github.com/infrapale/T2310_RFM69_TxRx

https://learn.sparkfun.com/tutorials/rfm69hcw-hookup-guide/all


Messages from Rx

  <#XuFabcdef..>\n
    X = RFM69 radio 
    u = unit address 0..7 
    F = 'S' Convert to sensor json
    F = '-' No conversion
  <#X1-Hello World>\n       -> Hello World
  <#X1SOD_1;Temp;23.1;->\n  -> {"Z":"OD_1","S":"Temp","V":23.1,"R":"-"}
  <#Ru

Check if a message has been received (Rx)
  <#Xu?>\n 
  reply:  <#XuNF>\n 
    N= messages in buffer   
    F = format of first message
    F = 'S' -> sensor json
    F = '-' -> Raw message  (default)

Read message from buffer
  First message =  {"Z":"OD_1","S":"Temp","V":23.1,"R":"-"}
  <#XuRF>\n

  <#X1R->\n -> {"Z":"OD_1","S":"Temp","V":23.1,"R":"-"}\n
  <#X1RS>\n -> OD_1;Temp;23.1;-\n

Set Mode for recived messages
  <#MuF>\n 
    F = 'J' -> json
    F = '-' -> Raw message  (default)


Sensor Message:  {"Z":"OD_1","S":"Temp","V":23.1,"R":"-"}
Relay Mesage      <#R12=x>   x:  0=off, 1=on, T=toggle
