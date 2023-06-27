# Folder Convention

An overview of a possible way of organizing project folders. 
Although this is quite general and might require tweaking or chewing in some specific cases, this is a good starting point to organize folder trees. 
Ideally, one would try to separate project folders trying to minimize connections to other folders (see [Modularity](https://www.16elt.com/2022/12/24/cohesion/)).

![Project Folder](www.plantuml.com/plantuml/png/RLR1Zjms3BtlLn1pQHR83j0UUoWID2sQGu8YpIL8WmLjqRQwiYH8z4wDelzU4Xfhh7K7Cy2Q8XyVdvxaVPCP4o-pkxkBs3_XI73wFOM_g6VuDJX3wGJ_tDq1r5M3Z1e3-Npz8fyF7zwz-mQOGLSUyz8DGUiauL_voLVZyF1riiQG__Rm4oJAY-EyHxs63i2FXdB_JR64n5ROWENKxu7aSGDvvGDJ5yBJsSRLT_SbcFja8v_ZsZv_Ae-djkRKj3hLsbD9hi-7l89vkjkO2wqcPR3ZagYHu1ggxACB_FZzEJ-FzqqW-YRmGyseWMY6-xl2y0RoWk8Dx3fB3HmoQvUIMGD7pDh-jCrz7Qh9MtnSEcVpH6O__owyQL3NgXr-3duKl7mg2J9pNVeIblJu4MUgIUSOMPKfJWHeCID6Iezv2eaVlPHLo5kEdKUeKMrMnb6PLEBZWj-qhv_JlkI5NlkYectXUk31z7VBmtfEuIpXXiJrU1pYC_4Kp35kREwNd6tmkjJIhXrUSDxrk566DjvMrEvjHOqVArfUUsMsWT2sb4yQEI99O4iuhCdUxgpnqWnDwj5-rTyxqpOb_-lmrjyA85-zS23PSM880-XT-ICyb3kpNAJGXyKPw0WkoKfkJ5BHCvap_EaVG6mFivQ39o5HxzyCji19_KpovC7OOQ14dk62QtuDtSAQGM0peDCO80DF15rW3lDPyTyF44FEjdFq6X1cOYpah2FeqIkn8IpUW26zzphhHxXC0cIrQRQ6WB2VIgTN8Tqetki47wcdd36jD-X8gMJdIKSNRZbe6tn6wr28d5_ATdMVAlTsO2d76DsgJD2lyaEtPYiJLqqlbYUTjFH1RxHNOl0urxRISSbaL0NuH96G5L2AAk1rQnoX0GuxVRSjq3OrND0pX39TLc3uHQGvR3GQeouZexkc3MLgsDvCX-5pwdNmtwG7N2hx9wAejRKETCUopWhb_IJqhYKNhO140_Oix8R5zso3px1SEMHwfeIkOXNkdoUR3zn7oy19B4-cE4nYFGhsueeSTjR341QEYz9lCDLkbTsOmWKwEq9G-3awsoChweohW5h-BWFRcO23X9u8S3jg1udAJQl-sFxSh1iTzcHWKYKmWzNjQS_AxaIzUcy8dLkLsXABD1iUPbMxN2IA4IKevQX2tXUvqgfKWqXPJlArzC2sUHNMhLt38W8w1nC-KtNO45BfMNPstpLh2Q2KPjQwIqXFwk3WbGwyTInE6IUmVBr0r7dUXt9kMEYbpCgu3t6L9hbSFdrnvZQtAlTQHhV-2R0B2oiUPW7RJelUpT0bzFsaWg5Q11B5e3JWZp2JJZ4ZwotamkLc8KN8IpyfdaEvmbLONcFcWsPLCDNhitGDdVuJQvz9LvM6KDU8Rl583EheTNFlaCBStEKSReZIwmrviypkFm00)


![test fig]([[data:image/jpeg;base64,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](https://en.wikipedia.org/wiki/Plant#/media/File:Cosmarium201512081550.JPG)](https://en.wikipedia.org/wiki/Plant#/media/File:Cosmarium201512081550.JPG))

![fig](https://en.wikipedia.org/wiki/Plant#/media/File:Cosmarium201512081550.JPG)

```
@startuml

package "Project Folder" {

  package "data" {
    [YYYYMMDD] as data_subfolder
  }
  
  data -[hidden]-> results
  package "results" {
    [YYYYMMDD_desc]
  }

  results -[hidden]-> src
  package "src" {
    (notebook.ipynb)
    (script.py)
    (script.R)
    "notebook.ipynb" -[hidden]-> "script.py"
    "script.py" -[hidden]-> "script.R"

  }

  src -[hidden]-> figures
  package "figures" {
    (plot_1.svg)
    (plot_1.png)
    (plot_2.svg)
    (plot_2.pdf)

    "plot_1.svg" -[hidden]-> "plot_1.png"
    "plot_1.png" -[hidden]-> "plot_2.svg"
    "plot_2.svg" -[hidden]-> "plot_2.pdf"
  }

  figures -[hidden]-> unpublished
  package "unpublished" {
    package "YYYYMMDD_Congress"{
      (YYYYMMDD_Your_Name_Congress.ppt)
    }
    
    package "paper_short_name"{
        package img {
          (figure_1.pdf)
          (figure_n.pdf)

          "figure_1.pdf" -[hidden]-> "figure_n.pdf"
        }

        package tex {
          (intro.tex)
          (results.tex)
          (methods.tex)
          (discussion.tex)

          "intro.tex" -[hidden]-> "results.tex"
          "results.tex" -[hidden]-> "methods.tex"
          "methods.tex" -[hidden]-> "discussion.tex"
        }
      (main.tex)

      "main.tex" -[hidden]-> tex
      "tex" -[hidden]-> img
    }
    paper_short_name -[hidden]-> "YYYYMMDD_Congress"
  }

  unpublished -[hidden]-> published
  package "published" {
  }

}

note right of data: - data folder could be write protected. \n- You might need subfolders if data comes in different ways, but date is always at the bottom.\n- If possible, a metadata file can be found describing what is inside each date (or subfolder). \nNecessary metadata per date should also be available.

note right of results: - After applying any analysis, a folder with the date and short name should be used.\n- Repeating the analysis could lead to different folders with different names or dates.\n- Each folder could be addressed in the lab notebook.

note right of src: - Here we should keep the notebook files and scripts were we would refactor functions used in several notebooks.\n- This folder could be git tracked, but be careful with image output of notebooks.\n- If scripts grow big or complicated, maybe it's time to make a package.

note right of figures: - figures can be placed here as is or in different subfolders (Ideally grouped in figures as the paper or presentation).\n- Try to overwrite figures.

note right of "unpublished": - Here you will have folders for papers and presentations you are still working on.\n- Although it might be annoying at first to copy paste processed figures here, think about it as being the main branch in a git repo.\n- Some formats allow git tracking such as latex or typst.

note right of published: - The objective of the project is get every folder from unpublished to published.

@enduml
```

```
@startuml
package "Other Project Folder" {
}
@enduml
```

```
@startuml
package "libs" {
  package "my_package" {
  }
}
@enduml
```
