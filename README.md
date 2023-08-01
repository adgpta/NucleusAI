# NucleusAI: GUI Application for Nuclei Segmentation and Features Extraction

NucleusAI provides a graphical user interface (GUI) platform to segment fluorescence images acquired from different microscopy techniques and extract radiomics features. This is applicable for both 2D and 3D images. Users can train their own segmentation models, validate the data and use the model to segment images in batches.

This documentation will guide users through the functionality of the GUI and how to use it effectively.

## Installation (Windows, Linux)

#### Conda Installation:

1. Download and install [anaconda](https://www.anaconda.com/) or [miniconda](https://docs.conda.io/en/latest/index.html) and [git](https://git-scm.com/downloads)

2. Open the conda terminal and clone the GitHub repository to a folder

   ```
   git clone https://github.com/adgpta/NucleusAI.git
   ```
   
3. **Conda**: Create a virtual environment with the provided environment files and install "requirements.txt" file using
   ```
   conda env create -f environments/Env.yml
   conda activate Stardist_GUI
   pip install -r requirements.txt
   ```
   OR in **IDE**: Open cloned repository as a new project. In terminal enter:
   ```
   pip install -r requirements.txt
   ```
 4. You can run the GUI by entering the following command:
   
      ```
      python NucleusAI.py
      ```

## Installation (Apple, tested on M1 chip)

1. Download and install [miniforge](https://github.com/conda-forge/miniforge)
2.  Open the conda terminal and clone the GitHub repository to a folder

   ```
   git clone https://github.com/adgpta/NucleusAI.git
   ```
3. **Conda**: Create a virtual environment
   ```
   conda create -y -n Stardist_GUI python=3.9
   conda activate Stardist_GUI
   conda install -c apple tensorflow-deps
   pip install -r requirements_apple_m1.txt
   ```
 4. You can run the GUI by entering the following command:
   
      ```
      python NucleusAI.py
      ```
------------------------------------------------------------------------------

> **TO NOTE:**
**_ If the installation process during the installation of PyQt5 shows an error, you have to install PyQt5 manually (via homebrew: brew install qt@5).
> Then the qmake path has to be added to the .zshrc (if you use Z shell): export PATH="$PATH:[PathToqmakebin-folder]" and the terminal has to be restarted and the conda environment needs to be actvated again.
> Then you have to install PyQt5 via: pip3 install PyQt5 --config-settings --confirm-license= --verbose
> After that, remove PyQt5 from the requirements file and restart the installation with pip install -r requirements_apple_m1.txt **_

------------------------------------------------------------------------------

      
## Guide:

Sample datasets and models are provided in [SampleData](https://github.com/adgpta/NucleusAI/tree/master/SampleData). 


1. Run the GUI by entering the following command:

   ```
   python NucleusAI.py
   ```
   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/e893fb36-6db7-43a8-9ab0-03fd3e3ec204">
   </div>

### _Training: Training your own StarDist models_

1. Select directories for raw images, labelled images and output.

   <div align = "center">  
      <img src="https://github.com/adgpta/NucleusAI/assets/77382748/897e71f6-3d84-408b-af17-ccf49bbb82ee">
   </div>

2. Select training parameters. The default valudes are provided. Tooltips are added for more description.

   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/ed37fda5-a18e-4de0-8231-270c2e5db249">
   </div>

3. Click `Train` to start training. Training parameters can be exported via `Export parameters`.

   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/73c78356-9331-4d51-9064-e897ae73b5ac">
   </div>

4. Training progress can be viewed in the terminal. Click on `Tensorboard` to view the dashboard with plots for the current training.
5. Click on the predict button to segment current files with the trained model. 

### _Validation: Checking the accuracy of the trained model._

1. Select directories for raw images, labelled images, output and the trained model.
2. Set the parameters (for 2D or 3D dataset).
3. Run `Validation`. The module will use the raw images and segmented them using the trained model. Validation is performed between the labelled images and the new automatically segmented images.
4. The output shows the validation accuracy of each file and overall statistics of all the input raw images.

   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/af8295a7-7e73-4110-a3bc-0d3e7473c713">
   </div>
   
5. Click on `Export` to export all validation statistics to a .csv file.

### _Segmentation: Segment fluorescent images._

1. Select directories for raw images and output and the trained model. Sample files can be found in [SampleData](https://github.com/adgpta/NucleusAI/tree/master/SampleData)
2. Set the parameters (for 2D or 3D dataset). 
3. Run `Segment`. The module will use the raw images and segmented them using the trained model and save the segmented masks in the output directory. The progress can be viewed in the terminal.
   
   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/3bd9e7a7-fac3-443b-9ef6-b778b871ebed">
   </div> 

### _Feature Extraction (based on Pyradiomics)_

1. Select directories for raw images, segmented masks and output.
2. Set the parameters (for 2D or 3D dataset).
3. Run `Extract Features`. The module will use the raw images and the segmented masks to extract radiomics features and save the data as `.csv` in the output directory.
  
  <div align = "center">  
      <img src="https://github.com/adgpta/NucleusAI/assets/77382748/4827e4b2-43d1-40fa-a1d9-509a40950753">
   </div> 
   
4. Sample extracted files can be found [here](https://github.com/adgpta/NucleusAI/tree/master/SampleData/PyradiomicsFiles).
   
## Image viewer:
The image viewer loads the images and masks from the input directories. The following video shows the available functions:

<div align = "center">  
   <video width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/3ef51726-14bb-4465-be6a-35dbf5b9b330">
</div>

## Known issues:


1. GUI crashes with the following error when running: (when installed using requirements.txt)

>Could not locate zlibwapi.dll. Please make sure it is in your library path!

**To resolve:** 
   
         a. Find a copy of the missing zlib DLL in the NVIDIA Nsight directory:
         
            `C:\Program Files\NVIDIA Corporation\Nsight Systems 2022.4.2\host-windows-x64\zlib.dll`
            
         b. Copy and rename it to:
         
            `C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin\zlibwapi.dll`

2. Tensorboard not live plotting in windows (In progress).
   Workaround: Refresh tensorboard reopening after training.

## Related links:

- StarDist (https://github.com/stardist/stardist)
- Weigert, Martin, Uwe Schmidt, Robert Haase, Ko Sugawara, and Gene Myers. 2020. “Star-Convex Polyhedra for 3D Object Detection and Segmentation in Microscopy.”
In 2020 IEEE Winter Conference on Applications of Computer Vision (WACV), 3655–62.
- Weigert, Martin, Uwe Schmidt, Tobias Boothe, Andreas Müller, Alexander Dibrov, Akanksha Jain, Benjamin Wilhelm, et al. 2018. “Content-Aware Image Restoration:
Pushing the Limits of Fluorescence Microscopy.” Nature Methods 15 (12): 1090–97.
