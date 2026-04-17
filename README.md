# Fume-Extractor-PCB-
4S battery, Noctua NF-A14 (or simular size and voltage), with a battery gauge.


### Battery Gauge 
To create the battery gauge, I used two voltage divider ladders composed of 5 resistors each. One ladder has 12V, and the other is connected directly to the battery. Then I used comparators so that it would compare the "fully charged" voltage, to a "depleted voltage". To do this, we had to scale 16.8V to 12V, since our battery is 4S and the other ladder is connected to a 12V buck converter. The scale is `12/16.8 = 0.7143`. 

Example Calculations: 
Suppose we have 5 resistors in series, R1, R2, ... If we know the voltages between the resistors (ie, V4 = 13.2V, V3 = 14.0V, V2 = 15.0V, V1 = 16.0V, scaled down to 12V, V4 = 9.43V, V3 = 10.00V, V2 = 10.71V, V1 = 11.43V) where V1 is between R1 and R2, and the battery (4S) is connected to the opposite side of R1. 

