Today is about trying new methods for getting a running photometry code. After reading [Marta's blog](https://gosnellgroup-marta.blogspot.com/) yesterday, the first thing that I thought was "this will be useful for learning astrometry," but I realized this morning that the process she went through to produce her code is almost exactly what I'm doing. So, I decided to use a few ideas that I got from reading her blog to help my coding today. I'll talk about it in "Working on Code." 

With these ideas in mind, I spent much of today going back through the first part of [photometry_practice_updated.py](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/photometry%20practice/photometry_practice_updated.py) (the first code I was working with) and beautifying it. I decided to create a new [folder](https://github.com/GosnellResearchGroupSummer2018/NGC6819/tree/master/photometry%20codes) called "photometry codes" in the [NGC6819 repo](https://github.com/GosnellResearchGroupSummer2018/NGC6819) that contains new, clean photometry codes that I've written. I'm still going to keep [photometry_practice_updated.py](https://github.com/GosnellResearchGroupSummer2018/NGC6819/blob/master/photometry%20practice/photometry_practice_updated.py) in the photometry practice [folder](https://github.com/GosnellResearchGroupSummer2018/NGC6819/tree/master/photometry%20practice) and continue to work on it as both a way to continuing to learn photometry and a way to keep a record of what I did while learning it, but the codes in [Photometry codes](https://github.com/GosnellResearchGroupSummer2018/NGC6819/tree/master/photometry_codes) will serve a different purpose. They'll be what we actually use on our data to extract onformation from the measurements. Moreover, there will be multiple codes because

## Working on Code
The first thing I realized after reading [Marta's blog](https://gosnellgroup-marta.blogspot.com/) is that so far I've been putting all my hope in this one code in trying to make it work, but in all honesty I don't think it's worth putting more effort than necessary into; I can use Google to find other codes or resources like astronomy.net to help me write this code. Anyway, I still need to spend some time learning more about the code in the first place before I can claim that I can that I can do photometry. Plus, I can frankenstein whatever new code I find in with the one I'm using to make something that actually works and that I understand. 

## Photutils Online Resource 
Marta helped me a lot with the code. She worked with me to get a way to make it iterative so the code processes all the .fits files in a particular directory and helped me 