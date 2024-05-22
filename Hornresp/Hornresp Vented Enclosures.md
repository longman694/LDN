# Simple
A vented sub is done just like a sealed sub, only you switch on the Rear Vented option in the Tools> Chamber tab. The only limitation is that it only allows for a single port at this time.  
  
Will will use a Vrc of 50, and Lrc of 30.1 from the sealed example above. You should start from here:  

![[Pasted image 20230803122910.png]]
  
  
OK, if you know your desired port dimensions enter them into the Ap and Lpt blocks, and Calculate. If you are unsure of that now start the Loudspeaker Wizard up, and play with the Ap and Lpt sliders while looking at the Response graph, until you like what you see. You will need to change the third dropdown bow from default to Combined here. Default with give you the Driver output only, Output 2 is the port only, and Combined is both. ![;)](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "Wink    ;)")  

![[Pasted image 20230803122919.png]]

  
I want you to really look at the pic above. Hornresp shows large peaks, and dips that you may not be use to seeing. These are the resonances caused by the main enclosure area, and the port. The peaks are exaggerated here as the program assumes totally solid materials. In real life the peaks and dips will not be as extreme, but they will be there in some fashion.  
  
When you like what you see save it, and the Calculate. When you open the SPL Response up it will default to the Default graph of the driver only.  
  
To change it go to Tools>Combined Response  

![[Pasted image 20230803122927.png]]

  
A new window will pop up.  

![[Pasted image 20230803122941.png]]
 
  
This is to set the amount of difference from your ears to the port mouth from the driver. The window does a good job of telling you how to do it, so follow the directions, or just leave it as 0.  

![[Pasted image 20230803122956.png]]

# Alternate Method

Here is an alternate way to sim a vented enclosure. The goal here is to get you thinking out of the box.  
  
In the last example we ended up with a rear enclosure of 50l 30.1cm deep, with a 200cm2 port 165cm long.  
  
All we have to do is move everything around to the other side of the driver. The port can be entered as S1 & S2 as 200, with L12 input as 165. The flare type doesn't matter here as there is no flare, so just leave it as Con.  
  
Now the main enclosure is input as the Throat Chamber. Enter the Vtc as 50000 (as it ic cc here, and not liters,) and the Atc requires a little math. All chambers are cylinders here, so you have the height and volume, but need the area of the top or bottom. Math skip... enter 1661.129 for Atc. ![;)](data:image/gif;base64,R0lGODlhAQABAIAAAAAAAP///yH5BAEAAAAALAAAAAABAAEAAAIBRAA7 "Wink    ;)")  
  
![[Pasted image 20230803123213.png]]
  
  
Notice the Schematic is flipped around here.  

![[Pasted image 20230803123229.png]]

![[Pasted image 20230803123234.png]]