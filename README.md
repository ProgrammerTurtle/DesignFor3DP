# DesignFor3DP
A guide on how to design functional 3D models for 3D printing production. This is not intended to be all inclusive and is certainly not the only way to design parts for manufacturing with 3DP. This is just the philosophy I follow when designing and it works well for me. Loosely based on a flyer guide by Billie Ruben. 


## 1. Wall Thickness

Wall thickness should, ideally, be a multiple of the extrusion width. Because FDM 3D printing operates off of a nozzle drawing "lines" of filament, those lines have a fixed width. For standard printing at 0.2mm layer height, you can assume an 0.4mm line width. So, your walls should be a multiple of 0.4mm. It should NOT be less than 0.4mm. Walls thinner than one line width will not print well, if at all. 

Generally, this does not matter much unless you are doing thin walls. If your wall is thicker than 2-3mm, you can basically forget this as the walls will start to have infill and not just be perimeters, which is where the majority of line width applies. 
t

Varying wall thicknesses, going from thicker to thinner. 


## 2. Overhangs

This is easily the most important aspect of designing for 3D printing. As mentioned earlier, FDM 3D printing operates off of a nozzle drawing "lines" of filament. These lines, generally, need to build off of other preexisting lines or the bed! Filament must be built upon exisiting material, otherwise it can droop or simply turn into a print failure as you have random blobs of plastic formed by the printer attempting to create floating layers. 

Not only does this apply to straight overhangs, but this also applies to vertically angled and curved features on the UNDERSIDE of a part. Too low of an angle means that there is too little filament to build upon in the previous layer, resulting in curling, waviness, or failed parts. This also applies to too much of a curve - generally, you can not curve all the way to vertical. 

An exception to this, of course, is bridging. Short unsupported sections can be completed by the printer as long as there is something to build off of at either end. This means cantilevers do not work, where only one end is supported. Generally, do not expect the printer to bridge distances larger than ~15mm. 
