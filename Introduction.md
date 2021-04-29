# Introduction

Welcome to Sinha lab's sa-working-directory (SymphonyAnalysis).

This project eases interaction with SymphonyAnalysis by:
* providing an easy way of setting project properties.
* interacting with multiple functionalities of SymphonyAnalysis.
* keeping up-to-date with latest changes in Github.

StartAnalysis is the main command used to start interacting with SymphonyAnalysis.

### User-defined properties in _myProperties.m_:
 * _experiment_data_directory_: local path to the folder containing .h5 symphony datasets
 * _experiment_name_:            name or name prefix of the .h5 data file(s)
 * _experimenter_name_:         name of the experimenter/analyzer

### Functionality
* Prepare project environment, global variables and necessary folders

* Parse and extract cell information from .h5 symphony files
  * **_StartAnalysis_** looks for previously parsed .mat cell files using _experiment_name_.
  * If no cell files found, it proceeds to parse .h5 file(s) located based on user-defined properties.
  * The parsed .mat cell files can be found under: _sa-working-directory/analysis/Projects/<experiment_name>\_temp/cells_
  * Once loaded, this folder path can be accessed in command window as:
    ```matlab
    global CELL_DATA_FOLDER
    CELL_DATA_FOLDER
    ```

* Load LabDataGUI
  * Once parsed cells are found under , **_StartAnalysis_** loads the cell data and starts **LabDataGUI**.
  * If user wants to open **LabDataGUI** for previously parsed cells:
    * Set appropriate value for _experiment_name_ under _myProperties.m_ and run
      ```
      StartAnalysis
      ```
  * If user wants to reopen accidentally closed **LabDataGUI** window:
    * If global variable _CELL_DATA_FOLDER_ is still defined, run
      ```
      LabDataGUI
      ```
    * Otherwise run
      ```
      StartAnalysis
      ```

