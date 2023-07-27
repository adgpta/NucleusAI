# NucleusAI: GUI Application for Nuclei Segmentation and Features Extraction

NucleusAI provides a graphical user interface (GUI) platform to segment fluorescence images acquired from different microscopy techniques and extract radiomics features. This is applicable for both 2D and 3D images. Users can train their own segmentation models, validate the data and use the model to segment images in batches.

This documentation will guide users through the functionality of the GUI and how to use it effectively.

## Installation

#### Conda Installation:

1. Download and install [anaconda](https://www.anaconda.com/) or [miniconda](https://docs.conda.io/en/latest/index.html) and [git](https://git-scm.com/downloads)

2. Open the conda terminal and clone the GitHub repository to a folder

   ```
   git clone https://github.com/adgpta/NucleusAI.git
   ```
   
4. **Conda**: Create a virtual environment and install "requirements.txt" file using
   ```
   conda create --name NucleusAI python=3.9
   conda activate NucleusAI
   pip install -r requirements.txt
   ```
   OR in **IDE**: Open cloned repository as a new project. In terminal enter:
   ```
   pip install -r requirements.txt
   ```
 5. **To install using environment files**: Navigate to the enviroment directory and run the following command to install NucleusAI dependencies. `YOUR_OS` is the name of the             operative system of the `.yml` file

      ```
      conda env create -f environment_YOUR_OS.yml
      ```

   

6. You can run the GUI by entering the following command:

   ```
   python NucleusAI.py
   ```

#### Prebuilt Versions:

We built an `.exe` file for Windows 10 to run the NucleusAI with Nvidia GPU resources and more will come for Apple MX chip and Linux OS:

- [Windows with Nvidia GPU support](https://www.dropbox.com/scl/fo/9ewk11zqelqf3hm6v08a3/h?rlkey=r7ckqk1cs7ar4s914whesi4h8&dl=0)
- Apple MX chip with GPU support (coming soon)
- Linux Ubuntu with Nvidia GPU support (coming soon)

Sample datasets and models are provided in [SampleData](https://github.com/adgpta/NucleusAI/tree/master/SampleData). 


## Guide:
1. Run the GUI by entering the following command:

   ```
   python NucleusAI.py
   ```
   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/f66d292b-95b7-47ad-8e75-b7098f0f5835">
   </div>

### _Training: For training your own StarDist models:_
1. Select directories for raw iamges, labelled images and output directory.

   <div align = "center">  
      <img src="https://github.com/adgpta/NucleusAI/assets/77382748/a324a9ea-4611-4e3d-9aae-a1b81682490f">
   </div>

2. Select training parameters. The default valudes are provided. Tooltips are added for more description.

   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/64514bb5-cfe0-43d0-bd0f-152c551d6fd2">
   </div>

3. Click "Train" to start training. Training parameters can be exported via "Export parameters".

   <div align = "center">  
      <img width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/3f56856f-762a-44d3-9773-bb450534f4ef">
   </div>

4. Training progress can be viewed in the terminal. Click on "Tensorboard" to view the dashboard with plots for the current training.
5. Click on the predict button to segment current files with the trained model. 

### Validation:
...
### Segmentation:

...

### Feature Extraction (based on Pyradiomics):

   
## Image viewer:
The image viewer loads the images and masks from the input directories. The following video shows the available functions:

<div align = "center">  
   <video width = 640 src="https://github.com/adgpta/NucleusAI/assets/77382748/069feb78-6cc1-4b9d-905d-660bb3c0dc94">
</div>



## Related links:

- StarDist (https://github.com/stardist/stardist)
- Weigert, Martin, Uwe Schmidt, Robert Haase, Ko Sugawara, and Gene Myers. 2020. “Star-Convex Polyhedra for 3D Object Detection and Segmentation in Microscopy.”
In 2020 IEEE Winter Conference on Applications of Computer Vision (WACV), 3655–62.
- Weigert, Martin, Uwe Schmidt, Tobias Boothe, Andreas Müller, Alexander Dibrov, Akanksha Jain, Benjamin Wilhelm, et al. 2018. “Content-Aware Image Restoration:
Pushing the Limits of Fluorescence Microscopy.” Nature Methods 15 (12): 1090–97.
