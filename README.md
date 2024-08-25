# Inverter Design and Analysis using Cadence Virtuoso
1. INVERTER Characteristics: <br/>
1.1. Creating the Schematic
1.2. Creating the Symbol of Inverter
1.3. Creating the symbol’s testbench
1.4. Analysis of Inverter (Transient, DC analysis)

2. Switching Threshold of Inverter (for same mid voltage for Vin=Vout=(Vdd/2))
3. Inverter same rise time and fall time (wpn for same rise time and fall time)
4. Noise Margin of Inverter

 INVERTER Characteristics:<br/>
   ![image](https://github.com/user-attachments/assets/d0a8ce0d-4a01-4a99-8040-654a0348797c) <br/>
   1.1. Creating the Schematic:<br/>
   Add instances like NMOS, PMOS, Vdc and ground joining then to form an inverter circuit.<br/>
   ![image](https://github.com/user-attachments/assets/8a2ee157-c582-4586-b1c3-5189db9f5c14) <br/>
   1.2. Creating the Symbol of Inverter:<br/>
   Created an inverter symbol from the schematic cell view.<br/>
   ![image](https://github.com/user-attachments/assets/70cd06d2-2fb1-4b5a-8705-92a8ade75cf0) <br/>
   1.3. Creating the symbol's testbench:<br/>
   Created a new cell view schematic and add the instance symbol of inverter and provide it with the required input voltages.<br/>
   ![image](https://github.com/user-attachments/assets/d084477b-3da7-492c-b201-c0db268ac73c) <br/>
   1.4. Analysis of Inverter(Transient,DC):<br/>
   Transient analysis: Variation of input and output wrt time.<br/>
   ![image](https://github.com/user-attachments/assets/4685a510-b2a1-4f47-b0c2-2b9ce0f3744d) <br/>
   DC analysis: Variation of output wrt input (Vin on x-axis).Input less than Vdd/2 considers it as logic 0 and gives us output as 1. Input greater than Vdd/2 considers it as logic 1 and gives us output as 0. An ideal inverter has switching threshold at half. i.e., we need output as Vdd/2 when input is also Vdd/2 i.e., for 0.9v we need to get output also 0.9v but here in the generated inverter we don’t have this picture.
   ![image](https://github.com/user-attachments/assets/ba1edd61-6fcf-49d2-a9cf-4de2e3f4ef24) <br/>
   Here for 900mv we are getting the output as 73.85mv and this is very far from an ideal inverter. But we can make the inverter close to the ideal one by changing the physical parameters of the MOSFETS.


   
   

   
   
   
   

   
