So, the Monday GRG meeting this morning made me realize that my data filtering is not up to par. The first thing I'm going to do is fix it. I do understand a little bit better what I'm going for now, and for Rory's sake I'll be detailed in this post about what I'm using to filter. I also have a better plan of attack for the rest of the week than usual. After fixing my data filtering comes converting the pixel coordinates in dolphot's output to RA and Dec for astrometric matching between different observations, matching the images, then making a color-magnitude diagram to finish out the summer.

# Data Filtering
So I'm just going to start over. The first two filtering steps will be the same -- getting rid of the individual data to focus on the overall data for a field and getting rid of anything that doesn't have an object type of 1 -- then I'm going to get rid of anything with sharpeness outside of -0.3 < sharpness < 0.3. Actually, let's do that now by typing ` awk '$7 >= -0.3 && $7 <= 0.3' goodstars.txt > notsharp.txt` and pressing enter in Ubuntu. I've now reduced the number of sources to 107,922.

For some reason I had a little bit of trouble installing Python. I hadn't yet needed it since changing my laptop so needed to get it again, which usually doesn't bother me because I like have a clean directory structure and delete things a lot. It seemed fine at first but then astropy wouldn't install properly, but I got through it. I just unistalled Anaconda, restarted my laptop because it was acting weird in other ways, too, and reinstalled Anaconda. That worked.

The reason I decided I needed Python again was to overlay where dolphot thinks the sources are onto the drc image so that I can check how things are going so far. I still am detecting ~100,000 sources so I already know I still have way too many (I'm looking for a number of stars about one order of magnitude smaller than what I have now), so the image is just purple (the color of the aperture objects). But, it's good to keep checking. 

![]({{ thom-ory.github.io }}/images/toomanysources.png)       
_I'm detecting about 50-100 times more sources than I should be_

---
I talked to Rory and got the values that he's using for the filtering so that we get the same sources in each image, meaning that I'll only accept quality flags of zero, the signal:noise should be greater than or equal to 75, and roundness and crowding should both be less than one. I might try to experimennt with the crowding value a little. 

After removing sources based on the above criteria, I end up with a document called 'finalsourcelist.txt' that has 1,326 sources and looks like this when overlayed the drc image:

![]({{ thom-ory.github.io }}/images/finalsourceimage_ib2o01.png)    
![]({{ thom-ory.github.io }}/images/[zoomed_right]finalsourceimage_ib2o01.png)    
![]({{ thom-ory.github.io }}/images/[zoomed_left]finalsourceimage_ib2o01.png)   
_Top: the entire field   
Middle: zoomed in on the top right corner   
Bottom: zoomed in on the bottom left corner_ 

---
I'm not happy with this, really. I need to tweak some of those parameters. There are so many stars in the diffraction spikes, and yet the code failed to detect many of the stars in open regions or is innaccurate in the positioning of the aperture. I think to get more stars in the open spots I'll drop the signal:noise to about 60, and to get rid of all those things in the diffraction spikes I'm going to reduce the crowding parameter to 0.75. There's now 1,375 sources, and here's how it looks:  

![]({{ thom-ory.github.io }}/images/finalsourceimage_ib2o01_2.png)
![]({{ thom-ory.github.io }}/images/[zoomed_right]finalsourceimage_ib2o01_2.png)
![]({{ thom-ory.github.io }}/images/[zoomed_left]finalsourceimage_ib2o01_2.png)
_same as above_

---
I'm pretty happy with those last images. There are still quite a few extra sources in diffraction spikes, but I'm getting almost all the sources that are in open areas. I might tweak those parameters a little more in the morning and try to get it closer to perfect, though I'll be satisfied with "quite good." Right now it's just "pretty good." If I can get it "very good" then we're cooking. I'm hoping that some of the bright sources that I didn't detect are just saturated pixels, and that seems likely (although I'm not entirely sure how to check that -- I'll figure it out). 

# Conclusion
Next step is filtering the rest of the data. Now that I know that the values Rory gave me worked a lot better on ib2o04 than ib2o01, I feel like it would be okay to have different parameters for each image, as long as Rory's and my parameters vary from image to image in the exact same way. Then I can start adding RA and Dec info. Rory tells me he has already done this in ib2o04, and Marta also knows whats up in this area, so it shouldn't be too bad. I see color-magnitude diagrams in my future!  
