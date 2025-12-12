# BARN_AirFilter
This project is for the BARN Laser Air Filter System.  It includes the filter box, filters and esphome components


The filter box is constructed fron 1/8" MDF
The filters are 
  UBeesize 12x24x1 Reusable Electrostatic Air Filter HVAC AC Furnace Filter,MERV 8,Washable, Lasts a Lifetime,Permanent Air Filter,Breathe Fresher,Home And Office(Actual Size:11.38x23.38x0.82 Inch)
  Nordic Pure 12x24x1 (11 1/2 x 23 1/2 x 3/4) Pleated Air Filters MERV 14 Plus Carbon 2 Pack

The ESPHome runs on the custom LolinS2Mini PCB

TechLabAirFilter.yaml 

The Adafruit LPS28 is used to measure the pressure https://www.adafruit.com/product/6067?gad_source=1&gad_campaignid=21079267614&gbraid=0AAAAADx9JvTfFg6rPxQX7ACpMkKxGuEvb&gclid=CjwKCAiAl-_JBhBjEiwAn3rN7TgxUI3Q1HDd7ACeudkuDa8KO3VnWLUQjoX-kVNkDqCcwqRsythILhoCm3YQAvD_BwE

The ESPHome library does not provide support for the LPS28 so we use a modified version of the LPS22 Library.
The only difference between the LPS28DFW and LPS22HB is the "WHO AN I" code returned by the chip.  To address this, the library code was modified to accept the LPS28DFW whcih returns a code of 0xB4
lps22.cpp
