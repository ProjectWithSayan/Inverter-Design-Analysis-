# Inverter Design and Analysis using Cadence Virtuoso
I. INVERTER Characteristics: <br/>
I.I. Creating the Schematic <br/>
I.II. Creating the Symbol of Inverter <br/>
I.III. Creating the symbol’s testbench <br/>
I.IV. Analysis of Inverter (Transient, DC analysis) <br/>

II. Switching Threshold of Inverter (for same mid voltage for Vin=Vout=(Vdd/2)) <br/>
III. Inverter same rise time and fall time (Wp for same rise time and fall time) <br/>
IV. Noise Margin of Inverter <br/><br/>

I. INVERTER Characteristics:<br/>
   ![image](https://github.com/user-attachments/assets/d0a8ce0d-4a01-4a99-8040-654a0348797c) <br/>
   I.I. Creating the Schematic:<br/>
   Add instances like NMOS, PMOS, Vdc and ground joining then to form an inverter circuit.<br/>
   ![image](https://github.com/user-attachments/assets/8a2ee157-c582-4586-b1c3-5189db9f5c14) <br/>
   I.II. Creating the Symbol of Inverter:<br/>
   Created an inverter symbol from the schematic cell view.<br/>
   ![image](https://github.com/user-attachments/assets/70cd06d2-2fb1-4b5a-8705-92a8ade75cf0) <br/>
   I.III. Creating the symbol's testbench:<br/>
   Created a new cell view schematic and add the instance symbol of inverter and provide it with the required input voltages.<br/>
   ![image](https://github.com/user-attachments/assets/d084477b-3da7-492c-b201-c0db268ac73c) <br/><br/>
   I.IV. Analysis of Inverter(Transient,DC):<br/>
   Transient analysis: Variation of input and output wrt time.<br/>
   ![image](https://github.com/user-attachments/assets/4685a510-b2a1-4f47-b0c2-2b9ce0f3744d) <br/>
   DC analysis: Variation of output wrt input (Vin on x-axis).Input less than Vdd/2 considers it as logic 0 and gives us output as 1. Input greater than Vdd/2 considers it as logic 1 and gives us output as 0. An ideal inverter has switching threshold at half. i.e., we need output as Vdd/2 when input is also Vdd/2 i.e., for 0.9v we need to get output also 0.9v but here in the generated inverter we don’t have this picture.
   ![image](https://github.com/user-attachments/assets/ba1edd61-6fcf-49d2-a9cf-4de2e3f4ef24) <br/>
   Here for 900mv we are getting the output as 73.85mv and this is very far from an ideal inverter. But we can make the inverter close to the ideal one by changing the physical parameters of the MOSFETS. <br/><br/>
   II. Switching Threshold of Inverter (for same mid voltage for Vin=Vout=(Vdd/2) <br/>
   ![image](https://github.com/user-attachments/assets/b781b18b-1214-4c90-8663-6bec492b29e1) <br/>
   There will be no effect on transient analysis. the graphs will be overlapped in the transient analysis. but in the dc analysis there will be multiple graphs producing outputs for different values of variable parameter(Wp).In the graph we can see multiple outputs for different values of Wp. The graph can be broken down to the plots that has Vout near 900mv.For the value Wp<5.63um, switching threshold can be obtained.Now we use the cross function from the calculator to verify it wrt the y-axis for that 900mv value and we get the value of Wp as 5.4589um to get the inverter to near ideal condition.<br/>
   ![image](https://github.com/user-attachments/assets/2cd3eb78-b14c-4023-bc0a-6df4bafcda2a) <br/>
   Wp=5.46um Wn=2um L=0.18um <br/><br/>
   III. Inverter same rise time and fall time (Wp for same rise time and fall time)<br/>
   We set the PMOS width to the value that we got above or any value and find the one plotted transient analysis and from this we use delay function two times one for input rising output falling gives the tpdf and input falling output rising gives the tpdr.<br/>
   ![image](https://github.com/user-attachments/assets/bd3052d4-b70d-4698-b544-d03aed9b3a66) <br/>
   The observed graph is for one variable value of Wp, it plots the rise delay and fall delay. The intersection has equal value of tpdf and tpdr.Plotted tpdr-tpdf & where tpdr-tpdf=0(calculate in calculator),that value is the desired value.<br/>
   ![image](https://github.com/user-attachments/assets/4dc3129a-8237-4220-a948-c41596fa0b8f)<br/>
   Wp=4.68um Wn=2um L=0.18um <br/>
   ![image](https://github.com/user-attachments/assets/157ab678-752a-4b21-8953-cdf4897231e6)<br/>
   tpdr value in calculator = 20.97E-12 units <br/>
   ![image](https://github.com/user-attachments/assets/e28097c8-b2ea-4c92-89dc-3144d2473da4)<br/>
   tpdf value in calculator = 21.09E-12 units <br/><br/>
   IV. Noise Margin of Inverter: <br/>
   We need to find Vil and Vih and to find them we do dc analysis and find the derivative equal to -1(2values will be found- big value Vih and small value Vil)(done using deriv function in calculator)<br/>
   ![image](https://github.com/user-attachments/assets/9313112b-952b-4bfb-ae59-be871ffe37fc) <br/>
   Vil=301.34mV , Vol=0V , NMl=Vil-Vol=301.34mV  <br/> Vih=1.5008V Voh=1.8V, NMh=Voh-Vih=0.2992V.<br/>






   
   

   
   
   
   

   
