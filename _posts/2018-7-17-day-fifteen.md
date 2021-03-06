After a hectic day, I'm finally able to sit down and work on photometry. Really quickly, before I start reading Rory's posts and learning DOLPHOT, I remade a few of the images that I posted yesterday so that I can give accurate information about the code that made them. Here's the [code](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/photometry%20codes/aperture_photometry.py), along with the results: 

**[sources_phot_table](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/first_attempt_at_HST_source_detection/day_seven/phot_table.txt)**    
![sources]({{ thom-ory.github.io }}/images/day_fifteen/sources.png)     
_FWHM = 3.0, Threshold = 5σ ("democratic" source detection, looking for most sources possible)_     

---
**[bright_sources_phot_table](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/first_attempt_at_HST_source_detection/day_seven/bright_phot_table.txt)**      
![bright_sources]({{ thom-ory.github.io }}/images/day_fifteen/bright_sources.png)         
_FWHM = 4.3, Threshold = 7σ ("oligargich" source detection, looking for brightest sources)_     

_**Note: When comparing the two raw images to the two that have the sources circled, you'll notice that they disagree on what the RA and Dec are. That's an error; the RA and Dec are correct on the raw images, but the images with circles on them contain information from an earlier test which do not correspond to that actual section of sky. All four images depict the same section of sky, RA = {-19:41:15.0244 U -19:41:15.6276}, Dec = {40:12:39.279 U 40:12:23.988}.**_

---
![fluxes]({{ thom-ory.github.io }}/images/day_fifteen/fluxes.png)       
_Fluxes according to [bright_sources_phot_table](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/first_attempt_at_HST_source_detection/day_seven/phot_table.txt). I decided that  bright_phot_table.txt represents better source detection. RA and Dec information are correct in this image_

---
Like has been the case so far, these codes are detecting extra sources around diffraction spikes, and are missing a few smaller sources. I'm planning on being more empirical about which FWHM I use by writing a code (tomorrow) that will actually determine the FWHM of the sources in the image. Hopefully, this will improve the source detection. 

## Learning DOLPHOT
To start, I will quickly read through Rory's posts for today and yesterday. He was just leaving the lab when I first got here and said that he felt that DOLPHOT was somewhat more difficult to learn than photutils had been. I suppose this isn't surprising because DOLPHOT is a PSF photometry program, as opposed to photutils whose aperture photometry utilizes a much more pedestrian version of background subtraction. Moreover, DOLPHOT is in C, not python, which might make learning it harder. 

Looking at DOLPHOT's [homepage](http://americano.dolphinsim.com/dolphot/), I see PSF and Pixel Area maps listed at the bottom. That's awesome; seems useful. I also see that there are two different versions of DOLPHOT, one for general PSF photometry applications, and another module specifically for Hubble. I'm going to look into the more general one first and move to using the Diafi data Dr. G gave us at the beginning of this project. I'm guessing that the Hubble module is a little harder to use, and I think the general version will prepare me for using that one. 

I downloaded the most recent version of DOLPHOT and saved the folder that it comes as to my desktop, right next to my github-connected directory. A quick glance at the contents of the folder reveals a bunch of .c executables, fewer .h executables, and some other folders with more, smaller executables. There's also the user guide hidden in there as a .pdf. I'm guessing these are modules that make up DOLPHOT which seems like it might be an amalgation of those modules, i.e. each exectuable has a task associated with photometry that DOLPHOT reads and combines to give results. To find out, I'm going to start reading the [user guide](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/dolphot_userguide.pdf), which I pushed to the [NGC6819 repo](https://github.com/GosnellResearchGroupSummer2018/NGC6819) for the group's convenience.

The introduction of the user guide mentions a paper by Dolphin himself that, according to the introduction, would be useful to read. It's cited as (Dolphin, A. E. 2000, PASP, 112, 1383), I'll come back to that once I get further in the reading. 

The first quick section is about installation, and it seems that I have to install a C/Fortran compiler called the GNU Compiler Collection (GCC) to run or install DOLPHOT. Before I waste too much time on that, I'm just going to continue reading the user guide. I'll come back to installing GCC tomorrow. 

After reading a bit more of the user guide, I'm not sure exactly what to do. There's a lot of jargon about GNU things that I can't understand. Rory seemed as confused as I am in his post, so I think it would be useful to wait until tomorrow morning to look at this so Rory and I can look through the manual together and make sense of it using two brains. 

# Conclusion
Today started late, but I got done what I needed to. Not only did I make up work that I was behind on yesterday, I also made that work better so that the images I posted today were improved from what I had to post on yesterday's blog entry. Finally, I started the process of learning DOLPHOT. I didn't make it very far, but I put enough into preparation today that I feel ready to tackle it tomorrow, so I'm happy. The goal of tomorrow, especially in the morning, will be learning more about DOLPHOT with Rory. The afternoon will be more focused on finding the real FWHMs for the images we're concerned with.  
