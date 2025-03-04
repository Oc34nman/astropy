# astropy

import numpy as np

import matplotlib.pyplot as plt

from astropy.io import fits

from astropy.utils.data import download_file

from astropy.visualization import LogStretch, PowerStretch

from astropy.visualization.mpl_normalize import ImageNormalize

image_file = download_file('http://data.astropy.org/tutorials/FITS-images/HorseHead.fits', cache=True)
image_data = fits.getdata(image_file)


import pprint
header = fits.getheader(image_file)
pprint.pprint(header)

plt.imshow(image_data, cmap='prism')
plt.show()

print('Min:', np.min(image_data))
print('Max:', np.max(image_data))
print('Mean:',np.mean(image_data))
print('Stdev:', np.std(image_data))

plt.figure(figsize=(10,10))
plt.imshow(image_data, cmap='cividis')
plt.colorbar()
plt.show()
