# Folder Convention

An overview of a possible way of organizing project folders. 
Although this is quite general and might require tweaking or chewing in some specific cases, this is a good starting point to organize folder trees. 
Ideally, one would try to separate project folders trying to minimize connections to other folders (see [Modularity](https://www.16elt.com/2022/12/24/cohesion/)).

![Project Folder](https://www.plantuml.com/plantuml/png/RLR1Zjms3BtlLn1pQHR83j0UUoWID2sQGu8YpIL8WmLjqRQwiYH8z4wDelzU4Xfhh7K7Cy2Q8XyVdvxaVPCP4o-pkxkBs3_XI73wFOM_g6VuDJX3wGJ_tDq1r5M3Z1e3-Npz8fyF7zwz-mQOGLSUyz8DGUiauL_voLVZyF1riiQG__Rm4oJAY-EyHxs63i2FXdB_JR64n5ROWENKxu7aSGDvvGDJ5yBJsSRLT_SbcFja8v_ZsZv_Ae-djkRKj3hLsbD9hi-7l89vkjkO2wqcPR3ZagYHu1ggxACB_FZzEJ-FzqqW-YRmGyseWMY6-xl2y0RoWk8Dx3fB3HmoQvUIMGD7pDh-jCrz7Qh9MtnSEcVpH6O__owyQL3NgXr-3duKl7mg2J9pNVeIblJu4MUgIUSOMPKfJWHeCID6Iezv2eaVlPHLo5kEdKUeKMrMnb6PLEBZWj-qhv_JlkI5NlkYectXUk31z7VBmtfEuIpXXiJrU1pYC_4Kp35kREwNd6tmkjJIhXrUSDxrk566DjvMrEvjHOqVArfUUsMsWT2sb4yQEI99O4iuhCdUxgpnqWnDwj5-rTyxqpOb_-lmrjyA85-zS23PSM880-XT-ICyb3kpNAJGXyKPw0WkoKfkJ5BHCvap_EaVG6mFivQ39o5HxzyCji19_KpovC7OOQ14dk62QtuDtSAQGM0peDCO80DF15rW3lDPyTyF44FEjdFq6X1cOYpah2FeqIkn8IpUW26zzphhHxXC0cIrQRQ6WB2VIgTN8Tqetki47wcdd36jD-X8gMJdIKSNRZbe6tn6wr28d5_ATdMVAlTsO2d76DsgJD2lyaEtPYiJLqqlbYUTjFH1RxHNOl0urxRISSbaL0NuH96G5L2AAk1rQnoX0GuxVRSjq3OrND0pX39TLc3uHQGvR3GQeouZexkc3MLgsDvCX-5pwdNmtwG7N2hx9wAejRKETCUopWhb_IJqhYKNhO140_Oix8R5zso3px1SEMHwfeIkOXNkdoUR3zn7oy19B4-cE4nYFGhsueeSTjR341QEYz9lCDLkbTsOmWKwEq9G-3awsoChweohW5h-BWFRcO23X9u8S3jg1udAJQl-sFxSh1iTzcHWKYKmWzNjQS_AxaIzUcy8dLkLsXABD1iUPbMxN2IA4IKevQX2tXUvqgfKWqXPJlArzC2sUHNMhLt38W8w1nC-KtNO45BfMNPstpLh2Q2KPjQwIqXFwk3WbGwyTInE6IUmVBr0r7dUXt9kMEYbpCgu3t6L9hbSFdrnvZQtAlTQHhV-2R0B2oiUPW7RJelUpT0bzFsaWg5Q11B5e3JWZp2JJZ4ZwotamkLc8KN8IpyfdaEvmbLONcFcWsPLCDNhitGDdVuJQvz9LvM6KDU8Rl583EheTNFlaCBStEKSReZIwmrviypkFm00.png)

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
