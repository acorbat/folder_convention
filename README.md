# Folder Convention

An overview of a possible way of organizing project folders. 
Although this is quite general and might require tweaking or chewing in some specific cases, this is a good starting point to organize folder trees. 
Ideally, one would try to separate project folders trying to minimize connections to other folders (see [Modularity](https://www.16elt.com/2022/12/24/cohesion/)).

Inside your Documents or Lab folder, you will have a separate folder for each project.
You will probably have a *libs* folder where you will keep all the packages you are currently working on.
These packages will be git tracked and pushed to your remote repository.
You often end up having a *misc* folder for random files as well.

## Project Folder

![Project Folder](https://www.plantuml.com/plantuml/png/TPF1RkCW48RlF0NAPK-rb3v0LMchlJMgzbPLbKLWRBF5W9XnjT4gxxxK9GJZ6Ca9cVzZvezdU4GIWQRHCFP3GIScGyn0HvmS3xeVY2iTG99sbZ4lv8VeWUzUWliJW_oNCmh2ZlzZZFEiAa7YAyRZwcQ2lyRr_FpqbA8vZcBq1jh38GkSYq2w4vAu7h_IlMM1nqWVsKCJWIw7tzFkpDBd_9I60k1a23SyjGfG9gceJk9eO5-K5rQO4sfihHXXFjH8_6JPH2w-U1aOPAfxJMsFEQrr14VdFXhjJ_R8lbCjQNz2cNcKGNjg_Eac6jRaxmH6OmjVdUwd0BZovWtjyRFFQRnnrEwR6AehPjpR5Uxj9dw_odw_cNtclUfgFeOs_jPa_NGq6WTGLRjtkTy_dUq38EvMFVUUP1ABnkU3hsuAxK6Ca5CqtbCz0N4jwdhX8RGuk43pwEIo6T5ZdxnMVcAJyWIczTstTf_VmQNwndbx-xojp-VzcTNs2FxUjgSj1TT4-PQOBjsMF08DJctAIgES4BMp2-ASTgpE9lGLFA-cOcicLYF11V88NtwMRDt6XBvyXTErLu84ltiRj59Wt-yUBk-W4Xuu1idYKuRIVMJfkvIAcMR5laIkGFJn25PDe_aF.png)


![Other Project Folder](https://www.plantuml.com/plantuml/png/ROynhi9034Hxdy9Ayw-HwhTm1HCxoOB9HbwxGhaxHaY8Y5WQ5_DcYkcRatdS5U2FPQHG1vNHqIjQcMP7BYQ3bxe0h3JSQ1BiJZwBuTdgDH7-LsMn3Xy0Y9yCazFBmxnyM-eRcxHGRxl4hjziUCDjPuzbYkmUeLZMk6Xfi_0H_eMGwcNXdFy4.png)


![libs](https://www.plantuml.com/plantuml/png/SoWkIImgAStDuIf8JCvEJ4zLKCh9J2fMKgZcKb202-LMnaFP48bQhbekXzIy5A0-0000.png)


**YYYYMMDD** refers to the date set in this format as it is automatically ordered.


## data

This folders contains all raw data files from experiments. 
They should be ordered according to the acquisition date, and inside, a subfolder for each sample. 
Remember that if a sample or glass contains several pieces or subsamples, you can use underscores to separate the names (*s_0_img_000.tiff*).
Try to keep naming convention across folders (at least inside same experiment types) as it makes it easier to parse attributes from filenames.
The convention of parameter name separated by underscore to its value is often good. For example sample 1, condition 2 and image 5 would be: *s_1_cond_2_img_005.tiff*.
Missing parameters can sometimes be ignored with a parser.

- data folder could be write protected.
- You might need subfolders if data comes in different ways, but date is always at the bottom.
- If possible, a metadata file can be found describing what is inside each date (or subfolder). 
- Necessary metadata per date should also be available.


## results

If some analytical step takes a long time and generates intermediate results that we wish to load quickly, these should be saved in this folder.
Sometimes we test different parameters or would like to update something after some time, so it is good to keep these in different folders.
If one of these folders is not accessed in a long time it can be either compressed or deleted.

- After applying any analysis, a folder with the date and short name should be used.
- Repeating the analysis could lead to different folders with different names or dates.
- Each folder could be addressed in the lab notebook.


## src

This is where the magic happens.

 - Here we should keep the notebook files and scripts.
 - Functions used in several notebooks should be refactored into the scripts.
 - This folder could be git tracked, but be careful with image output of notebooks.
 - If scripts grow big or complicated, maybe it's time to make a package and move it to libs.


## figures

Figures can be placed here as is or in different subfolders (ideally grouped in figures as the paper or presentation).
Try to overwrite figures so that this folder does not grow as crazy.
It is often better to see the figure inside a notebook or IDE, and then export here the close to final version.

**TIP**: Always set the actual size of the figure inside your code!!!
This will reduce a lot the time needed to correct font sizes and how to fit it into panels of figures.


## unpublished

Here you will have folders for papers and presentations you are still working on.
Although it might be annoying at first to copy paste processed figures here, think about it as being the main branch in a git repo.
Regarding figures, only copy here the final version that will be uploaded to the paper (probably pdf).
Some formats allow git tracking such as latex or typst.
Latex Beamers for example are easy to git track and possible choice intead of powerpoint.
You might also want to make a notebook in slide format, but this is hardcore.


## published

The objective of the project is get every folder from unpublished to published.
You will know when to move folders here.
