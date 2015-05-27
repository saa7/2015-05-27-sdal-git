#computational-project-cookie-cutter
A cookie cutter (aka project template) to set up a folder structure for a computational project.
This is a quick way to setup a folder structure that follows one standard to organize a project.
This helps with project management, reproducibility, sharing, and publishing your data, analysis, and results.

This project was inspired (and modeled off) by:

[Noble WS 2009 A Quick Guide to Organizing Computational Biology Projects. PLoS Comput Biol 5 7: e1000424. doi:10.1371/journal.pcbi.1000424](http://dx.doi.org/10.1371/journal.pcbi.1000424)

## What it does
the `setup_project_dir.sh` script creates the following folder structure:

        PROJECTNAME                        # In the format of: TYPE_YYYYMM_PROJECTNAME (see below for more details)
        |- docs/                           # directory for documentation, one subdirectory for manuscript
        |  |- project/                     # project descrption and the admin docs; include project_name_description.txt
        |  |- meetings/
        |  |- lit/                         # reference materials
        |  |- proposal/
        |     |- solicit/                  # the research solicitation (e.g. RFP, RFI) and related material
        |     |- examples/                 # other successful proposals
        |     |- staff
        |     |- budget
        |     |- figures/
        |     |- drafts/
        |        +- DRAFTS                 # see below on DRAFTS formatting
        |
        |- data/                           # data for storing fixed data sets (see below)
        |  |- 1_original/                  # originally received data stored as read-only/nonvolatile
        |  |- 2_working/
        |  |- 3_tidy/                      # original data that has been tranformed to 3rd Normal Form (e.g. tidyR) format (see below)
        |  +- 4_clean/                     # data that has been cleaned and transformed for specific analysis
        |
        |- analysis/                       # any source code, this includes code to clean data sets
        |  |- username                     # home directories for project user code
        |     |- code/                     # subset your code by language
        |     |  |- R/
        |     |  |- PY/
        |     |  |- SAS/
        |     |  +- HACKS/
        |     |
        |     |- results/
        |        +- YYYMMDD_NAME_VER.TYPE  # see below for formatting
        |
        |- present/                        # presentations
        |
        |- report|paper|program/
        |  +- YYYMMDD_NAME_STATUS[_VER]    # see below for formatting
        |
        |- scratch/                        # temporary files that can be safely deleted or lost
        |- README                          # the top level description of content
        |- study.Rmd                       # executable Rmarkdown for this study, if applicable
        |- Makefile                        # executable Makefile for this study, if applicable
        |- study.Rproj                     # RStudio project for this study, if applicable
        |- datapackage.json                # metadata for the (input and output) data files

    #####PROJECTNAME
        Syntax: TYPE_YYYYMM_PROJECTNAME
        Options: TYPE = {PRJ "Project", PAP "Paper", PRG "Program", RES "Resource", MSC "Miscellaneous"}
        Example: PRJ_201503_MYPROJECT

    #####DRAFTS
        Syntax: YYYYMMDD_NAME_STATUS[_VER]
        Options: STATUS = {DRAFT, FINAL}
        Example: 20150622_myproposal_draft_v3.docx

    #####RESULTS
        Syntax: YYYYMMDD_NAME_VER.TYPE
        Example: 20150819_mynewdataset_v2.csv
        Example: 20150819_mystatresults_v5.txt

    #####REPORT|PAPER|PROGRAM
        Syntax: YYYYMMDD_NAME_STATUS[_VER]
        Options: STATUS = {DRAFT, FINAL}
        Example: 20150622_myreport_final.docx
        Example: 20150419_myprogram_v3.py

    #####--DATA--TIDY
        TIDY data has been transformed from raw archived data into 3rd Normal Form (e.g. TidyR Protocol)
        1 -Each variable forms a column.
        2 -Each observation forms a row.
        3 -Each type of observational unit forms a table.
        The data file can be a .csv or a database query file (e.g. .R, .py, .sql).
        A descriptive metadata file in .json format should be included with each base dataset.

A README containing a brief blurb is placed in each folder.
This is because git will not track empty folders and placing a README will
remind you of what goes in each folder, and also the overall
folder structure will be retained

If you use a webservice in conjunction with your version control (e.g. github, bitbucket, gitlabs, gitbucket, etc)
the webservice will be able to render these README and other [markdown](https://help.github.com/articles/markdown-basics/) files automatically.

This project was taken from [this](https://github.com/chendaniely/computational-project-cookie-cutter) github repo
