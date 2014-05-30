Codebook for quantifying 390nm intensity of bacteria, using ImageJ (1.48 for mac).
====

1. Under ImageJ, **open** the figure to be analysed.
2. Convert to RGB: **Image**->**Type**->**RGB Color**.
3. Make a copy: **Image**->**Duplicate**.
4. Use the copy to create a binary image: **Image**->**Adjust**->**Threshold**. Slide the bar to get desired structures.
5. **Process**->**Subtract** background with rolling ball may help there are highlighting too many “noise” or background pixels. 
6. Once it shows desired structures, click 'Apply' on the Threshold window.
7. If you have particles that have merged together, **Process**->**Binary Watershed** can often (but not always) accurately cut them apart by adding a 1 pixel thick line where it feels the division should be. (Not very applicable in our case)
8. Use **Analyze**->**Set Measurements** and set the “Redirect to” line to the name of the copy of the image that is still grayscale. If you don’t do this, your intensity values will be read from the binary image, and they will all be 255! Checking *display label* will label your data table with the image name and particle number. Use the checkboxes to select which grey value statistics you want from your image.
9. Click on the binary image to select it, then go to **Analyze**->**Analyze Particles**.
10. Select the copy, invert the colour (**Edit**->**Invert**), and **Threshold** again as above, to select background. 
11. Now you can normalise the data to the background.

Many of the materials are based on [link](http://www.unige.ch/medecine/bioimaging/tricks/imagejtutorials/Quantification.pdf).