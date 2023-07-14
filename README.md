# PYNQ-SDIMAGE-ZYBO OLD (NOT FOR ZYBO Z7!!!)
 <img src="https://github.com/Lcrypto/PYNQ-SDIMAGE-ZYBO/blob/main/zybo-old.png" width="405" height="326">

PYNQ 2.1 SDIMAGE for  ZYBO (old) with Z-7010   (Ubuntu 18.04.5 LTS bionic)
1. Download image from https://drive.google.com/file/d/13zinkK1EtF_g5ySr_o1me8-X7PB9LwHQ/view?usp=sharing
2. write image on microsd
3. copy to boot disk files  BOOT.bin, devicetree.dtb, uImage,  boot.py from folder  "kernel Pynq 2.1 for boot partition".
boot.py        -    Use at boot to blink by led on board using pynq overlay
BOOT.bin        -   Binary boot file, which includes the Zynq bitstream, FirstStageBootLoader and U-boot
uImage          -   Kernel image file
devicetree.dtb  -   device tree blob

Run board from microsd and use SMB(\\192.168.2.99) and jupyter by Ethernet 192.168.2.99 (login xilinx and passw xilinx )
4.  DMA overlay
This overlay implements a AXI stream dma that transfers data from one address in the memory to another. It is based on the following reference:

Lauri's Blog - AXI Direct Memory Access : 	https://lauri.xn--vsandi-pxa.com/hdl/zynq/xilinx-dma.html

The <a href="https://github.com/altuSemi/PYNQ4Zybo/tree/master/overlays/dma" target="_blank"> dma overlay</a> was designed in Vivado 2016.3.
A python c extension was designed to pass data from python to the PL and back via the AXI dma, based on the c code in the above blog. This extension is currently supporting a max buffer length of 16K word (unit32).

The package is installed by copying the <a href="https://github.com/altuSemi/PYNQ4Zybo/tree/master/dma" target="_blank">dma</a> directory to the board (via the samba server), and executing inside the dma directory:
```
pip3.6 install . 
```
The code of the dma package is based on Lauri's Blog above, as well as the following references:

Returning a numphy array from c: 		http://acooke.org/cute/ExampleCod0.html

Enhancing Python with Custom C Extensions:	https://stackabuse.com/enhancing-python-with-custom-c-extensions/

5. FIR Filter example


 <img src="https://github.com/Lcrypto/PYNQ-SDIMAGE-ZYBO/blob/main/filter%20BD.png" width="405" height="326">
 <img src="https://github.com/Lcrypto/PYNQ-SDIMAGE-ZYBO/blob/main/filter%20BD.png" width="405" height="326">
