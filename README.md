# combine-amira-tifs
Fiji toool to allow combining multiple segmentation tifs into one, while maintaining unique ids for each segmented object. In particular, it is meant for combining 8-bit or 16-bit tifs collected with amira into a single 16 bit image. It does so by sequentially adding images together, but before each sequential image is added, the maximum of the combined image is added to the incoming image.

## Installation
1. Download `Combine_Amira_Tifs.bsh`. 
2. Go to Fiji->Plugins->Install, navigate to and select `Combine_Amira_Tifs.bsh` (ensure it installs in the plugins directory)
3. Restart Fiji

## Running the plugin
The plugin should now appear in the plugins dropdown as "Combine Amira Tifs".

When you run the script, you will be able to choose the source directory which should contain (but does not need to be limited to) the tifs which you want to combine. You can also select the output directory where you want the combined image saved. 

There is also a field for entering a [regex](https://web.mit.edu/hackl/www/lab/turkshop/slides/regex-cheatsheet.pdf) for pattern matching your files, if they are not the only files in the directory.

For example if the File Pattern was set to `crop\d+_labels_\d+\_.*\.tif`, it would include all tifs of the form `crop_{some_digits}\_labels_{some_digits}_{anything}.tif`. 

Or `crop_\d+.tif` would find any tif files of the form crop_{some_number}.tif.

Or, `.*.tif` would find any tif files.