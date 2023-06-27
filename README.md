# Folder Convention

An overview of a possible way of organizing project folders. 
Although this is quite general and might require tweaking or chewing in some specific cases, this is a good starting point to organize folder trees. 
Ideally, one would try to separate project folders trying to minimize connections to other folders (see [Modularity](https://www.16elt.com/2022/12/24/cohesion/)).

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
