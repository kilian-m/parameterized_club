# 3D printed parameterized juggling club optimized for low weight


The club is modeled in Autodesk Fusion 360. It is parameterized meaning there is a list of parameters like core_length, body_wall_thickness, waves_number... that you can change and the model will adjust accordingly (at least that is the idea, some parameter combination are not sensible, but there sometimes are errors even for sensible parameter combinations, I do not know if this is due to my poor modeling skills or bugs in Fusion).
The current parameter set has the rough shape of a Henrys Pirouette / Loop and is very light (~100g, most people say to light, to be a good juggling club) and spins slowly. I tried to give the parameters meaningful names. If something is not clear ask me or just change it and see what happens.

## Materials

### Knob, outer Top, Ring: 
- varioshore TPU (https://colorfabb.com/de/varioshore-tpu-green) - this has a texture that is quite similar to Henrys tops/knobs

### inner Top
- PCTG

### Handle:
- Nylon/PA12 (https://fiberlogy.com/de/filamente/nylon-pa12/)
- PA is semiflex so it has some give but should be not so brittle that it breaks
- I get a matte surface finish from this which feels very nice (some people say that it is to slippery but I have not found a grippy semiflex filament yet. maybe dip it in liquid rubber?)

### Body:
- PP (https://www.3djake.de/fiberlogy/pp-light-green, https://www.3djake.de/formfutura/centaur-pp-natural, https://www.ppprint.de/produkt/p-filament-721-mint-green/), formfutura seems to have the best layer adhesion
- PP is semiflex so it does not break easily and it is rigid enough to be caught on the body (at least with the wave pattern)
- also tried PA12, this is a lot stiffer and feels better if caught on the body, but it results in strong vibrations and therefore very noisy clubs

### Carbon_adapter:
- PP (probably does not matter)

## How I print

### Knob, outer Top, Ring:
- layer height: .2 mm, line width: .4 mm, nozzle temperature: 220 C, build plate temperature: 40 C, print speed 30 mm/s, flow 57%, use print cooling, 70% infill
- .4 mm nozzle
- use supports

### inner Top
- standard PCTG settings

### Handle:
- layer height: .1, nozzle temperature: 270, build plate temperature: 85 C, print speed 20 mm/s, no print cooling
- make shure to use a printer that can handle such temperatures!!!
- use .4 mm nozzle
- use Magigoo PA on your build plate
- use thick brim for build plate adhesion (initial layer height .3 mm)
- import 'Handle' and 'Handle_adapter' to your slicer
- group models, center it with the top end facing down, set line width to .8 mm
- slice and export G-code
- set line width to .4 mm
- slice in vase mode ('spiralize outer contour' in cura) and export G-code
- in your favourite text editor copy together G-code from vase mode code (above 'Handle_adapter') and solid code (below bottom of 'Handle'), if you use relative steps this should work if you use absolute coordinates make shure to set the E distance to the last value of the solid G-code with the M92 command
- print

### Body:
- layer height: .3 mm, nozzle temperature: 230 C, build plate temperature: 30 C, print speed: 30 mm/s, print cooling depending on pp brand
- use .4 mm nozzle
- stick clear packing tape on your build plate, PP adheres to nothing else
- do not use build plate adhesion structure like brim or skirt
- import 'body' and 'body_adapter' to your slicer
- group models, center it with the top end facing down
- slice with .4 mm line width and export G-code
- ungroup models, delete 'body_adapter'
- slice in vase mode ('spiralize outer contour' in cura) with .8 mm line width and export G-code
- in your favourite text editor copy together G-code from vase mode code (everywhere with a wall thickness of .8 in the model) and merged code (everywhere else), if you use relative steps this should work if you use absolute coordinates make shure to set the E distance to the last value of the deleted G-code with the M92 command
- print

- (use .6 mm wall thickness if you use PA)

### Carbon_adapter:
- slice with PP settings
- add pause at the top end of the hexagonal cavity (13 mm)
- during printing add M3 nut


## Assembly

### Components
- printed parts
- carbon fiber tube inner diameter 8 mm, outer diameter 10 mm, length 500 mm  (https://www.amazon.de/dp/B07RSYHL3F?psc=1&ref=ppx_yo2ov_dt_b_product_details)
- 2x M3 nuts (embedded in carbon_adapter), 2x M3x20 bolt (https://www.schraubenluchs.de/100-Stueck-Linsenflanschschrauben-ISO-7380-2-A2-M3-x-20)
- 2x washer (inner: 5.3 mm, outer: 15 mm)
- clamp (https://www.schellen-shop.de/schlauchbefestigung/cobra-schellen/cobra-schellen-bandbreite-8-mm-edelstahl-v2a?number=2000000126447)

### Process
- use acrylic glue / superglue to fix carbon adapter in carbon fiber tube
- put ring over handle
- stick body in top
- stick handle in knob
- put carbon fiber tube in handle, close clamp with pliers
- put washers in top and knob
- attach body to handle/carbon fiber tube
- screw in M3 bolts, put in nubsies

## TODOs
- there is z-banding on the bottom half of the handle because of bed slinging, a semiflex material and a tall print with a small footprint. The only solution to this is probably using a core-xy or delta printer



<br>
<br>
This work is licensed under CC BY-NC-SA 4.0 