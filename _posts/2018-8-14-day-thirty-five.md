Today was about finishing up the data filtering and starting to get a code that can match sources between images. Like I predicted yesterday, each image's best source detection occurred under slightly different parameters. I found that the crowding and signal:noise parameters gave me the best control over the image and allowed me to balance between too many source in diffraction spikes and not enough sources in open areas. 

Reading a [page](http://docs.astropy.org/en/stable/coordinates/matchsep.html#matching-catalogs) Dr. G sent to us about catalog matching with astropy, I realize there are going to be two main steps in this code: 

1. Create a catalog of stars for each image with a line something like this: `c = SkyCoord(ra=ra1*u.degree, dec=dec1*u.degree)` where `ra1` and `dec1` are numpy arrays containg pixel coordinates for detected soures. 

2. Find the least distance between sources in the two catalogs. I think Marta has already done something like this, but I can also see that astropy has som built in functionality in this regard with a command called `match_to_catalog_sky()`.

I feel really solid on the foundation of what I'm supposed to do with this code, but I was never able to make it work properly. I think astropy is not working properly based on the types of error messages I'm getting, so I'm going to try to reinstall or update it and see how that goes.

# Conclusion
Today was a little bit frustrating; it was going smooth all morning as I was fixing my data filtering and I thought this was going to cnotinue through to catalog matching since I had a pretty solid idea of what I needed to do to make the code work, but I got caught out by the coding and haven't gotten results yet. I should get them fairly quickly tomorrow, however, since I already have a good start. 
