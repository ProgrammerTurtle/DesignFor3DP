# DesignFor3DP
A guide on how to design functional 3D models for 3D printing production. This is not intended to be all inclusive and is certainly not the only way to design parts for manufacturing with 3DP. This is just the philosophy I follow when designing and it works well for me. Loosely based on a flyer guide by Billie Ruben. 


## Introduction

Hi! My name is Parker and I have been doing 3D printing for the majority of my life. Almost 12 years, actually. I started in First Grade with a Makerbot Replicator at my school, and fell in love immediately. From there, I eventually got my first personal printer in Middle School. I now own 7 or 8 different printers, including a few fully custom designed ones. 

This is my guide for how to design parts that can be FDM printed well. These are all things I have learned over the years - hopefully, I can help others learn it a bit quicker than I did! 

I have 2 design philosphies that I follow with my parts: **Make it look cool** and **never ever use supports unless ABSOLUTELY necessary** (they rarely are) - You should be using supports for less than 5% of prints! 


## 1. Wall Thickness

<img width="820" height="1010" alt="20260811-0140-19 0192431" src="https://github.com/user-attachments/assets/6e4cd2ee-e21b-410c-aafe-048528ec7420" />

- Wall thickness should, ideally, be a multiple of the extrusion width. Because FDM 3D printing operates off of a nozzle drawing "lines" of filament, those lines have a fixed width. For standard printing at 0.2mm layer height, you can assume an 0.4mm line width. So, your walls should be a multiple of 0.4mm. It should NOT be less than 0.4mm. Walls thinner than one line width will not print well, if at all. 

- Generally, this does not matter much unless you are doing thin walls. If your wall is thicker than 2-3mm, you can basically forget this as the walls will start to have infill and not just be perimeters, which is where the majority of line width applies. 

- NOTE: Nowadays, we do have a wonderful slicer feature called Arachne, which changes line width to adjust for differing sizes. This makes it significantly less important to pay attention to line width, but it is still good practice to at least keep it in mind as often times perimiter/vertical line count is associated with strength. It is especially crucial to keep in mind not going below 1x line width. 


## 2. Overhangs

<img width="1205" height="856" alt="image" src="https://github.com/user-attachments/assets/9f3e200d-bedc-4706-98fe-310b6619d86c" />

- This is easily the most important aspect of designing for 3D printing. As mentioned earlier, FDM 3D printing operates off of a nozzle drawing "lines" of filament. These lines, generally, need to build off of other preexisting lines or the bed! Filament must be built upon exisiting material, otherwise it can droop or simply turn into a print failure as you have random blobs of plastic formed by the printer attempting to create floating layers. 

<img width="1521" height="942" alt="image" src="https://github.com/user-attachments/assets/6e0f1d5c-ce25-4468-9880-39adc0ab0764" />

- Not only does this apply to straight overhangs, but this also applies to vertically angled and curved features on the **underside** of a part. Too low of an angle means that there is too little filament to build upon in the previous layer, resulting in curling, waviness, or failed parts. This also applies to too much of a curve - generally, you can not curve all the way to vertical. 

<img width="1164" height="881" alt="image" src="https://github.com/user-attachments/assets/41bf48a0-0897-4109-968e-6c021cf8f59c" />

- An exception to this, of course, is bridging. Short unsupported sections can be completed by the printer as long as there is something to build off of at either end. This means cantilevers do not work, where only one end is supported. Generally, do not expect the printer to bridge distances larger than ~15mm. 


## 3. Holes and Arches

<img width="1409" height="1017" alt="image" src="https://github.com/user-attachments/assets/4ae00126-56d9-43fe-9bad-7c8278192e02" />

- This is actually fairly similar to overhangs if you think about it - they are just complete curves. Vertical holes will print fine with no issues. Horizontal holes, however, are a different story. The top of the hole is what we consider a **steep overhang**. This means it will not print very well. So, we can make the holes print better by turning them into a teardrop shape - when done correctly, this will not noticeably affect quality or performance.

- Fun fact about teardropped holes - they are actually the [RepRap Logo](https://reprap.org/wiki/RepRapLogo)! RepRap is an important movement from the early days of consumer 3D printing and is the reason that all of modern 3D printing exists. It was all about easy to source, self replicating 3D printers, so that we could get machines to the masses. Really, really important piece of history, and it happens to be this exact technique! 

<img width="1068" height="839" alt="image" src="https://github.com/user-attachments/assets/e2786879-b62f-4671-aba1-1fd705e11c4c" />

- The same applies to arches! They are essentially an incomplete circle. Point the top, and the print will come out perfect! 

<img width="1064" height="899" alt="image" src="https://github.com/user-attachments/assets/e93a6b61-6253-41e7-9e26-39114ee2e810" />

- Another technique you can use for holes, specifically holes you are pressing components into, is hexagonal holes! A good example would be for bearing holes where you want a good press fit - often times, a hexagon will be more accurate than a round bore. Especially on vertical walls. This is because at the end of the day all circles are approximations, not actual circles. Some of them are really, really good approximations, but it is still an approximation. A hexagon is straight lines and exact angles - nothing to mess up. 

## 4. Tolerances

<img width="1383" height="783" alt="image" src="https://github.com/user-attachments/assets/bf81564a-875a-4144-bc0f-2adf217cba19" />

- Tolerances are one that catches a lot of people off guard, even though it makes a lot of sense in hindsight. Your printer is working its absolute hardest to be accurate - so accurate, that if you have a hole and a pin that are the same size in CAD, they won't fit together without a lot of force! You have to add **tolerance**, aka a gap that allows for the parts to fit together cleanly. For most parts, an 0.3mm gap will be enough. On vertical features, you may need a bit more tolerance due to less accuracy in Z. These apply to **any parts that need to fit together**

- Tolerances also apply to print-in-place prints and other multi-part assemblies that print in one go. They must be added so that parts do not fuse together, allowing for proper motion and seperation. An example of this would be an articulated flexy dragon - everyone has seen one of those. Proper tolerancing on the joints is what allows motion. 


## 5. Fillets and Chamfers

<img width="1004" height="990" alt="image" src="https://github.com/user-attachments/assets/124cacee-f2b5-40ec-840b-d7a150ec6cb9" />

- Vertical fillets should be used on corners when possible. These help reduce inertia during direction changes and result in a cleaner print overall. 

<img width="854" height="1115" alt="image" src="https://github.com/user-attachments/assets/b19c1093-2d38-4149-a0a1-20a15c708d70" />

- Horizontal fillets can be tricky when on the bottom of parts - they result in the curved under surface mentioned earlier, which causes a steep overhang that is hard to print. 

<img width="1056" height="1092" alt="image" src="https://github.com/user-attachments/assets/3f020730-08c5-460b-90e2-3bce94d9f5cb" />

- Standard horizontal chamfers work on both the top and bottom of a part. These are called **equal chamfers** - the amount the chamfer extends in either direction is equal, always resulting in a 45 degree angle. Which is easily printable!

<img width="897" height="1116" alt="image" src="https://github.com/user-attachments/assets/6ae46cf6-7acd-4e78-8687-6314edf84449" />

- Horizontal chamfers and fillets can be combined to negate the steep overhang but still have a curved finish, even if it is a bit "false"

<img width="1001" height="1030" alt="image" src="https://github.com/user-attachments/assets/c40cf16b-a1a5-4ed2-b27b-5314f4656312" />

- Chamfers or fillets should be added to the base of vertical walls to strengthen the joint - otherwise, you are at a big risk of the part snapping!


## 6. Print Orientation

<img width="1460" height="1137" alt="image" src="https://github.com/user-attachments/assets/46d2aa8f-aac6-49ea-a8e3-a6d2a04177d0" />

- When designing a part for 3D Printing, you should always have a print orientation in mind. You should be thinking about which side will be on the bed, which sides will be walls, which side should be the top, etc. This can take a bit to get the hang of, but it is the true key to 3DP design. Once you understand your print orientation, you can fine tune strength, quality, tolerances, and more. 

- Parts will always be weaker in Z than they are in XY. This should be considered when you are making your part - if you need it to be strong, the forces should be top down, not on the side. That way, you aren't splitting at layers, but rather compressing layers together. 

<img width="1456" height="1005" alt="image" src="https://github.com/user-attachments/assets/8413228c-8e43-44a4-8f06-9776f65958a0" />

- Print orientation also matters for curves! Layers will almost always be taller than the resolution your printer can achieve in XY - so, vertical curves will look like stair steps! 
