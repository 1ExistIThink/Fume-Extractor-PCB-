# Fume-Extractor-PCB-
4S battery, Noctua NF-A14 (or simular size and voltage), with a battery gauge.


### Battery Gauge 
To create the battery gauge, I used two voltage divider ladders composed of 5 resistors each. One ladder has 12V, and the other is connected directly to the battery. Then I used comparators so that it would compare the "fully charged" voltage, to a "depleted voltage". To do this, we had to scale 16.8V to 12V, since our battery is 4S and the other ladder is connected to a 12V buck converter. The scale is `12/16.8 = 0.7143`. 

Example Calculations: 
    
    Suppose we have 5 resistors in series, R1, R2, etc. If we know the voltages between the resistors: 
    
    `V4 = 13.2V, V3 = 14.0V, V2 = 15.0V, V1 = 16.0V, scaled down to 12V my multiplying by 0.7143, V4 = 9.43V, V3 = 10.00V, V2 = 10.71V, V1 = 11.43V`
    
    Where V1 is between R1 and R2, and the battery (4S) is connected to the opposite side of R1. 
    Find the resistor values. 
    
    First, finding the voltage between the resistors:
    
    `VR1 = 12.0 - 11.43 = 0.57V, VR2 = 11.43 - 10.71 = 0.72V, VR3 = 10.71 - 10.00 = 0.71V, VR4 = 10.00 - 9.43 = 0.57V, VR5 = 9.43 - 0 = 9.43V`
    
    Therefore since the current through all resistors is the same:
    
    `R1​:R2​:R3​:R4​:R5​ = 0.57:0.72:0.71:0.57:9.43` -> normalize by R/0.57 -> `R1:R2:R3:R4:R5 = 1:1.26:1.25:1:16.54`
    
    Meaning, we can choose any size resistors as long as they follow this ratio. For simplicity sake, I will be using R1 = 1k, R2 = 1.26k, R3 = 1.25k, etc. Note that these resistor values will be the same for both ladders         because of the scaling factor from earlier. 
