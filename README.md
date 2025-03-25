# Data Visualization with `ggplot2`

## About The Coffee, Cookie and Coding $\left(C^3\right)$ Workshops

Yale's Public Health Data Science and Data Equity (DSDE) team created this workshop series for Public Health and Biostatistics masters-level students at Yale. They are designed to help learners effectively leverage computational tools and analytical methods in their educational and professional endeavors. You can find out more about past and upcoming tutorials on our YouTube (coming soon) and [website](https://ysph.yale.edu/public-health-research-and-practice/research-centers-and-initiatives/public-health-data-science-and-data-equity/events/).


## About Workshop

**Workshop Title:** &nbsp; Data Visualization with `ggplot2`

**Date:** &emsp;&emsp;&emsp;&emsp;&emsp;&nbsp; Thursday March $27^{\text{th}}$, 2025

Upon completing the workshop, you will be able to:
- Classify the Grammar of Graphics layers used in `ggplot` syntax.
- Utilize `ggplot2` for common tasks, including applications of different geometries, effective use of layering, and polishing the result.
- Applying `ggplot2` to make interactive plots, map projections, and leverage AI-assisted coding.

You can find out more about past and upcoming tutorials on our YouTube (coming soon) and [website](https://ysph.yale.edu/public-health-research-and-practice/research-centers-and-initiatives/public-health-data-science-and-data-equity/events/). If you are affiliated with Yale, you can set up an office hour appointment with one of the data scientists ([Bookings Page](https://outlook.office365.com/owa/calendar/DataScienceDataEquityOfficeHours@yale.edu/bookings/)).

## About Repository

This is the only repository associated with this workshop. It contains all of the relevant code, the data set, and a PDF of the slide deck that was used in the workshop. Limited comments were added to the slide deck PDF. Users who wish to see these extra commentaries will need to download the PDF to their local device.

### Overview Of Contents

- **Worked Through Example:** the *.qmd file constitues the code used to generate the *.html report
- **Worked Through Example - associated files:** "Images" directory
- **For cleaning and preparing the data:** "Data Cleaning" directory
- **The dataset used in the workshop:** `RSV-NET Infections.gz.parquet`
- **Code for the workshop discussions and challenge questions:** `Discussion and Challenge Questions.R`
- **R version:** 4.4.4
- ``renv`` is included to reproduce the environment.

**NOTE:** The cleaning script has already been run to generate the necessary files. Users of this repository will only need to open the `Discussion and Challenge Questions.R` and `Worked Through Example.qmd` scripts. To get the most use out of the `Worked Through Example.qmd`, you will need to render the code to view the *.html output locally. This format provides the most accessible way to view its contents.

## Using this Repository

### Making a Clean-Break Copy

The repository needs to be copied into your personal GitHub for the workshop in a manner that will decouple its operations from this original repository. Please use one of the following two methods to do this.

**METHOD 1:** Copying Using GitHub Importer

**NOTE:** This method is not a Fork. You can learn more about GitHub Importer [here](https://docs.github.com/en/migrations/importing-source-code/using-github-importer/importing-a-repository-with-github-importer).

1. Under the "Repositories" tab of your personal GitHub page, select the "New" button in the top-right corner. This will start the process of starting a new repository.

2. At the top of the page is a hyperlink to import a repository. Open that link ([GitHub Importer](https://github.com/new/import)).

3. Paste the URL of this repository when prompted. No credentials are required for this action.

4. Adjust the GitHub account owner as needed and create the name for the new repository. We recommend initially setting the repository to Private.

5. Proceed with cloning the newly copied repository.

**METHOD 2:** Copying Using Terminal

These directions follow GitHub's [duplicating a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/duplicating-a-repository) page.

1. [Create a new](https://github.com/new) GitHub repository ([Further documentation](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)).
   
   **NOTE:** Do not use a template or include a description, README file, .gitignore, or license. Only adjust the GitHub account owner as needed and create the name for the new repository. We recommend initially setting the repository to Private.
   
2. Open Terminal.

3. Navigate to the file location you want to store the repository copy.
   ```
   cd "/file_location/"
   ```

4. Clone a bare copy of the repository.
   ```
   # using SSH
   git clone --bare git@github.com:ysph-dsde/Data-Visualization-with-ggplot2.git
   
   # or using HTTPS
   git clone --bare https://github.com/ysph-dsde/Data-Visualization-with-ggplot2.git
   ```
   
5. Open the project file.
   ```
   cd "Data-Visualization-with-ggplot2.git"
   ```
   
6. Push a mirror of the cloned Git file to your newly created GitHub repository.
   ```
   # using SSH
   git push --mirror git@github.com:EXAMPLE-USER/NEW-REPOSITORY.git

   # or using HTTPS
   git push --mirror https://github.com/EXAMPLE-USER/NEW-REPOSITORY.git
   ```

7. Delete the bare cloned file used to create a new remote repository.
   ```
   cd ..                                               # Go back one file location
   rm -rf Data-Visualization-with-ggplot2.git          # Delete the bare clone
   ```
8. Proceed with cloning the newly copied repository.

### Cloning the Copied Repository

Now that you have copied this repository into your own GitHub, you are ready to proceed with a standard clone to your local device.
  
1. Open Terminal.

2. Navigate to the file location you want to store the repository copy.
   ```
   cd "/file_location/"
   ```
3. Clone the newly created GitHub repository.
   ```
   # using SSH
   git clone git@github.com:EXAMPLE-USER/NEW-REPOSITORY.git

   # or using HTTPS
   git clone https://github.com/EXAMPLE-USER/NEW-REPOSITORY.git
   ```

4. **OPTIONAL:** You can reset the repository history, which will clear the previous commits, by running the following block of code (Source: [StackExchange by Zeelot](https://stackoverflow.com/questions/9683279/make-the-current-commit-the-only-initial-commit-in-a-git-repository)).
    ```
    git checkout --orphan tempBranch         # Create a temporary branch
    git add -A                               # Add all files and commit them
    git commit -m "Reset the repo"
    git branch -D main                       # Deletes the main branch
    git branch -m main                       # Rename the current branch to main
    git push -f origin main                  # Force push main branch to GitHub
    git gc --aggressive --prune=all          # Remove the old files
    ```

### Initializing the Environment

1. Open the newly cloned file.
2. Launch the project by opening `JHU-CRC-Vaccinations.Rproj`.
3. Open `Analysis Script_Vaccinations Time-Series Plot.R`.
4. In the R console, activate the enviroment by runing:
    ```
    renv::restore()
    ```

   **NOTE:** You may need to run ``renv::restore()`` twice to initialize and install all the packages listed in the lockfile. Follow the prompts that comes up and accept intillation of all packages. You are ready to proceed when running ``renv::restore()`` gives the output ``- The library is already synchronized with the lockfile.``. You can read more about ``renv()`` in their [vignette](https://rstudio.github.io/renv/articles/renv.html).

## About Original Data Source

This workshop uses the Center for Disease Control's (CDC) [Respiratory Syncytial Virus Hospitalization Surveillance Network (RSV-NET)](https://www.cdc.gov/rsv/php/surveillance/rsv-net.html) surveillance data. It is one of the CDC's Respiratory Virus Hospitalization Surveillance Network (RESP-NET) Emerging Infections Programs (EIP). This version was downloaded from [data.gov](https://data.cdc.gov/Public-Health-Surveillance/Weekly-Rates-of-Laboratory-Confirmed-RSV-Hospitali/29hc-w46k/about_data) in January of 2025. RSV-NET conducts active, population-based surveillance for laboratory-confirmed RSV-associated hospitalizations. It contains stratification for geolocation, race/ethnicity, age, and sex.

The cleaned and harmonized version of the RSV-NET dataset was compiled as part of the YSPH’s very own PopHIVE project. You will see that its contents differ slightly from what you would see on the data.gov website. Special thanks to [Professor Daniel Weinberger](https://ysph.yale.edu/profile/daniel-weinberger/) for allow us to adopt his plot code in this workshop.
