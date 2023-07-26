# NucleusAI: GUI Application for Nuclei Segmentation and Features Extraction

NucleusAI provides a graphical user interface (GUI) platform to segment fluorescence images acquired from different microscopy techniques and extract radiomics features. This is applicable for both 2D and 3D images. Users can train their own segmentation models, validate the data and use the model to segment images in batches.

This documentation will guide users through the functionality of the GUI and how to use it effectively.

## Installation

#### Conda Installation:

1. Download and install [anaconda](https://www.anaconda.com/) or [miniconda](https://docs.conda.io/en/latest/index.html) and [git](https://git-scm.com/downloads)

2. Open the conda terminal and clone the GitHub repository to a folder

   `git clone https://github.com/adgpta/NucleusAI.git`
   
3. **Conda**: Create a virtual environment and install "requirements.txt" file using
   ```
   conda create --name NucleusAI python=3.9
   conda activate NucleusAI
   pip install -r requirements.txt
   
   ```
   OR in **IDE**: Open cloned repository as a new project. In terminal enter:
   ```
   pip install -r requirements.txt
   
   ```
4. 
5. Navigate to the enviroment directory and run the following command to install NucleusAI dependencies:

   `conda env create -f environment_YOUR_OS.yml`

   YOUR_OS: is the name of the operative system of the `.yml` file

6. You can run the NucleusAI by running the following command:

   `python NucleusAI.py `

#### Prebuilt Versions:

We built an `.exe` file for Windows 10 to run the NucleusAI with Nvidia GPU resources and more will come for Apple MX chip and Linux OS:

- [Windows with Nvidia GPU support](https://www.dropbox.com/scl/fo/9ewk11zqelqf3hm6v08a3/h?rlkey=r7ckqk1cs7ar4s914whesi4h8&dl=0)
- Apple MX chip with GPU support (coming soon)
- Linux Ubuntu with Nvidia GPU support (coming soon)

A sample dataset can be dowloaded here:
JN please give a link



## Step-by-step NucleusAI Workflow Description:

###### Training:
...
###### Validation:
...
###### Prediction:

...

###### Feature Extraction (based on PyRad):

...

Video tutorials will be available soon.



## Related links:

- StarDist (https://github.com/stardist/stardist)
- Weigert, Martin, Uwe Schmidt, Robert Haase, Ko Sugawara, and Gene Myers. 2020. “Star-Convex Polyhedra for 3D Object Detection and Segmentation in Microscopy.”
In 2020 IEEE Winter Conference on Applications of Computer Vision (WACV), 3655–62.
- Weigert, Martin, Uwe Schmidt, Tobias Boothe, Andreas Müller, Alexander Dibrov, Akanksha Jain, Benjamin Wilhelm, et al. 2018. “Content-Aware Image Restoration:
Pushing the Limits of Fluorescence Microscopy.” Nature Methods 15 (12): 1090–97.
