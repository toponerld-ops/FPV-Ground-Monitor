# FPV GROUND STATION — Journal Export

- Exported at: 2026-05-25T13:59:48Z
- Project ID: 3503
- Entries: 17

## Entry 1
- ID: 7588
- Author: toponerld
- Created At: 2026-05-17T11:36:19Z

### Content

Started the uHAT schematic for the July FPV Monitor in EasyEDA Pro. The uHAT sits on top of the Radxa Zero 3W's 40-pin GPIO header and handles all the power management for the monitor.
Today I completed the power input block. The battery connects through a KF301-2P screw terminal, goes through a fuse for protection, and into an MP2307DN buck converter that steps the 11.1V 3S li ion battery down to a clean 5V rail. Added input and output filtering caps, bootstrap cap, soft start cap, freewheeling SS34 Schottky diode, and a resistor divider on the FB pin set for 5V output.
Next up: 40-pin GPIO header for the Radxa Zero 3W and the USB-A socket for the RTL8812AU WiFi dongle.
![Screenshot 2026-05-17 165958.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTY1NTYsInB1ciI6ImJsb2JfaWQifX0=--fdaffce1448d20b1cb28ee1bfea8e379769626f0/Screenshot 2026-05-17 165958.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/X917GN-vhyAR/timelapse-X917GN-vhyAR.mp4

## Entry 2
- ID: 7595
- Author: toponerld
- Created At: 2026-05-17T12:15:31Z

### Content

Added the Radxa Zero 3W 40-pin GPIO header (IDC-SMD_40P-P2.54) and mapped all used pins 5V power input, GND, 3.3V, I2C for OLED, UART for debug, and 6 GPIO pins for buttons and LEDs. Remaining pins got no-connect markers.
Added a USB 3.0 Type-A vertical socket for the RTL8812AU WiFi dongle. Connected VBUS to +5V, GND, and routed D+ and D- to pins 27 and 28 on the GPIO header. SS pins no-connected since Zero 3W GPIO only exposes USB 2.0.
Next: buttons, LEDs and OLED 
![Screenshot 2026-05-17 174520.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTY1NzAsInB1ciI6ImJsb2JfaWQifX0=--7fac8375a263ce41ee8114f8ea5ffe4da103d857/Screenshot 2026-05-17 174520.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/cNxJUGiLqJAZ/timelapse-cNxJUGiLqJAZ.mp4

## Entry 3
- ID: 7601
- Author: toponerld
- Created At: 2026-05-17T12:54:14Z

### Content

Added the interface components on page 3. Placed a 4-pin header for the SSD1306 OLED module connected to I2C (SCL/SDA) with 3.3V and GND.
Added 4 tactile buttons (TS-1187A-B-A-B) -- 3 for UI navigation and 1 dedicated power button. Each has a 10K pulldown resistor to ensure clean LOW reads when unpressed.
For LEDs went with 3x WS2812B-V5 addressable RGB LEDs instead of plain single color -- all controlled from a single GPIO pin via data chaining. Each LED has a dedicated role: link status, recording status, and battery level. Added 100nF decoupling caps on each.
DRC passed with 0 errors on all 3 pages.
Next: PCB layout.
![Screenshot 2026-05-17 182300.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTY1OTAsInB1ciI6ImJsb2JfaWQifX0=--210b78b8be5825a3ed131792d20bfa487aed5739/Screenshot 2026-05-17 182300.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/5m16LrcEGvKj/timelapse-5m16LrcEGvKj.mp4

## Entry 4
- ID: 7637
- Author: toponerld
- Created At: 2026-05-17T16:38:28Z

### Content

Finished the schematic and started tracing the pcb looks like i have a lot to learn in tracing will take help
![Screenshot 2026-05-17 220814.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTY2NTMsInB1ciI6ImJsb2JfaWQifX0=--6034614c2575a2a3805db783d1e33c8f5a4471a0/Screenshot 2026-05-17 220814.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/uewIPvZDGqOo/timelapse-uewIPvZDGqOo.mp4

## Entry 5
- ID: 8815
- Author: toponerld
- Created At: 2026-05-24T07:38:45Z

### Content

soooooo i forgot to save and i lost my traced pcb so i made it again and have no errors in drc and have a few errors in dfm so have to fix those 
![Screenshot 2026-05-24 130830.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk0NTIsInB1ciI6ImJsb2JfaWQifX0=--9a24b52c28f44bbcf9bb55cca120d18ef45e6f9d/Screenshot 2026-05-24 130830.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/6hfgF1i-I5Ng/timelapse-6hfgF1i-I5Ng.mp4
- https://public.lapse-hackclub.link/timelapses/8OSZpo_ioEFw/timelapse-8OSZpo_ioEFw.mp4

## Entry 6
- ID: 8825
- Author: toponerld
- Created At: 2026-05-24T09:02:11Z

### Content

okayy so finished everything only silkscreen errors in dfm so the pcb is done!!!! now its time to build it heheheh.
![Screenshot 2026-05-24 142334.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk0NzAsInB1ciI6ImJsb2JfaWQifX0=--8a783865240e2ff2a4c4e1cf4b00aa962a9132b7/Screenshot 2026-05-24 142334.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/la_aP5qNe96_/timelapse-la_aP5qNe96_.mp4

## Entry 7
- ID: 8861
- Author: toponerld
- Created At: 2026-05-24T13:12:09Z

### Content

Im making the outer case for the fpv ground station i paused a lot in between cause i was taking measurements from the PCB i made 
![Screenshot 2026-05-24 183717.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk1NzYsInB1ciI6ImJsb2JfaWQifX0=--517fb251c06571c6763a873605657e1b9bac3303/Screenshot 2026-05-24 183717.png)
![Screenshot 2026-05-24 184144.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk1ODEsInB1ciI6ImJsb2JfaWQifX0=--5f39765c8d0093a2f3b4a0436a5a8f4ebb3e353f/Screenshot 2026-05-24 184144.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/Htptf2LEvjc1/timelapse-Htptf2LEvjc1.mp4

## Entry 8
- ID: 8873
- Author: toponerld
- Created At: 2026-05-24T14:32:58Z

### Content

major changes looks like i messed up the button, led and the connector holes and then i added the step files of the components then assembled them now i have to make the holes for them then it will be done heheh.
![Screenshot 2026-05-24 200159.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk2MTYsInB1ciI6ImJsb2JfaWQifX0=--33e68714304786991e781bf6ed2b33e01f5506f2/Screenshot 2026-05-24 200159.png)
![Screenshot 2026-05-24 200247.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk2MTcsInB1ciI6ImJsb2JfaWQifX0=--b3326edc6d4aec21421c1747040147808586ff9e/Screenshot 2026-05-24 200247.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/Tq5StU_N6Mgt/timelapse-Tq5StU_N6Mgt.mp4

## Entry 9
- ID: 8889
- Author: toponerld
- Created At: 2026-05-24T15:41:06Z

### Content

uhhhhhhhhhhhh i cant seem to find how to make holes to the case according to the pcb i made on the case!!
![Screenshot 2026-05-24 211056.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk2NjksInB1ciI6ImJsb2JfaWQifX0=--42138603029b576afba2d5e7825aa6d36d7f5de4/Screenshot 2026-05-24 211056.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/W3pzDga-OvNf/timelapse-W3pzDga-OvNf.mp4

## Entry 10
- ID: 8916
- Author: toponerld
- Created At: 2026-05-24T16:59:24Z

### Content

sooooo i finished the holes for the pcb buttons and ledsss finnally i can sleep i grinded alott today gettin closer to the goal imma give my very best so that i can go to sz!!
![Screenshot 2026-05-24 222402.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk3MTYsInB1ciI6ImJsb2JfaWQifX0=--efb7eba06e1ebd64293d3786d862292f4e5f4513/Screenshot 2026-05-24 222402.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/qM8SKp4SDo91/timelapse-qM8SKp4SDo91.mp4

## Entry 11
- ID: 9014
- Author: toponerld
- Created At: 2026-05-25T02:22:44Z

### Content

made the antennas or the case and added support brackets and mounting holes for the radax pi zero w3 
![Screenshot 2026-05-25 075218.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk5NDMsInB1ciI6ImJsb2JfaWQifX0=--e165107124990388a89ef7f7555995ab71fee000/Screenshot 2026-05-25 075218.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/9Zzg_7UHkDmC/timelapse-9Zzg_7UHkDmC.mp4

## Entry 12
- ID: 9023
- Author: toponerld
- Created At: 2026-05-25T03:32:46Z

### Content

soo i finished everything now making the repo so i made the BOM and uploaded all the files then set up lfs cause the files were too big and made the repo clean. i have to finalize the BOM and submit!!
![Screenshot 2026-05-25 083422.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MTk5NjksInB1ciI6ImJsb2JfaWQifX0=--9f571ea5c75348e9454ac431670be14fea4e76fc/Screenshot 2026-05-25 083422.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/kwZ2xxx-BgNz/timelapse-kwZ2xxx-BgNz.mp4

## Entry 13
- ID: 9040
- Author: toponerld
- Created At: 2026-05-25T04:48:32Z

### Content

im havin problems with jlcpcb looks llike sm of my components are out of stock so i got fedup and started making the zine page will complete soon, wish me luck!
![Screenshot 2026-05-25 101821.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAwMDMsInB1ciI6ImJsb2JfaWQifX0=--5f78821d5d47a6daa439b81843ce79ea2665c043/Screenshot 2026-05-25 101821.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/U2qUrNBQRouZ/timelapse-U2qUrNBQRouZ.mp4

## Entry 14
- ID: 9063
- Author: toponerld
- Created At: 2026-05-25T08:35:56Z

### Content

Made the zine pagee put a lot of effort into itt and a bit of advice from krishh!! it looks good hope it will get printed
![FPV (1).png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAwNjcsInB1ciI6ImJsb2JfaWQifX0=--c615b7703d2a354620e3c377474a6aa31c95b751/FPV (1).png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/IqYz93zXrst4/timelapse-IqYz93zXrst4.mp4

## Entry 15
- ID: 9073
- Author: toponerld
- Created At: 2026-05-25T09:42:43Z

### Content

I completed the zine before but missed a couple of things like the name age country a brief discription so ive added those now
![ZINE.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAwOTIsInB1ciI6ImJsb2JfaWQifX0=--fc6638d6464c652e048fee26c3a277f753f29db0/ZINE.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/jWElGVDbj_cF/timelapse-jWElGVDbj_cF.mp4

## Entry 16
- ID: 9086
- Author: toponerld
- Created At: 2026-05-25T10:49:25Z

### Content

I removed all the components from the top side of the pcb and place them all on the bottom side to cut costs, it was a lot of workkk
![Screenshot 2026-05-25 161907.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAxMTksInB1ciI6ImJsb2JfaWQifX0=--3daf25c29b42161fe9bf32c077189410060d6de4/Screenshot 2026-05-25 161907.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/EmE-8jUR9670/timelapse-EmE-8jUR9670.mp4

## Entry 17
- ID: 9104
- Author: toponerld
- Created At: 2026-05-25T13:02:16Z

### Content

So i found out that unlike BP Fallout allows grants for tools so instead of spending 150$ on a pcba i decided to do sm research on tools. and i also made alot of additions and changes to the github repo
![Screenshot 2026-05-25 183156.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAxNTcsInB1ciI6ImJsb2JfaWQifX0=--ee24430fb4dd9fc5241e9da6aa0ff5e7c310b987/Screenshot 2026-05-25 183156.png)
![Screenshot 2026-05-25 173958.png](/user-attachments/blobs/redirect/eyJfcmFpbHMiOnsiZGF0YSI6MjAxNTgsInB1ciI6ImJsb2JfaWQifX0=--1a725eb48700ed9154a8e2ba4ecc4901ec4c4893/Screenshot 2026-05-25 173958.png)


### Recording Links

- https://public.lapse-hackclub.link/timelapses/0TN58jZo2xLi/timelapse-0TN58jZo2xLi.mp4
