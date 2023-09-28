# Data quality and incidental findings

:::{note}
In this page how to check the quality of your data and how to deal with incidental findings
:::

Data quality is an important step that should happen immediately after a dataset has been transferred from the MRI/MEG facilities. Ideally data quality happens on the same day of the scanning.

## How to assess the data quality of MRI images

There are various resources on the web that describe the types of artifacts for various MRI modalities. The most common ones are related to artifacts due to head motion, artifacts related to signal intensity (e.g. signal drop in a part of the image, large effect of the scanner field).

### Step by step process on how to verify data quality for MRI images

:::{warning}
Please note that at this stage the DICOM files contain the full 3D image of the face of the individual which is a strong identifier (facial recognition tools work really well with faces reconstructed from MRI images ADDLINK). Handle them with care.
:::

#### 1. Convert the DICOM files to NIFTI format.

For the sole purpose of data quality assurance, this step is not necessary. However, your further steps in data analysis will most likely use the NIFTI file format. There are various tools to convert the data to NIFTI. Here we choose dcm2niix as a powerful tool that can also generate BIDS compatible files.

How to install dcm2niix on your department workstation or on a VDI virtual machine. 

- The advantage of using a computer that is physically in the Aalto network is that you do not need to move back-and-forth large DICOM files.
- Add here the steps for installing and converting


#### 2. Open the MRI images

This is one way of doing it on VDI linux, but feel free to use your favourite software.

- Log in into https://vdi.aalto.fi and choose Ubuntu (no NVIDIA)
- Open a shell terminal and type the command `kinit`. This will ask for your Aalto password. This step is needed to make sure the VDI machine has access to your project data
- Within the terminal, navigate to the folder where your data are stored. For example with command `cd /m/nbe/project/MYPROJECT/rawdata/`
- Open the MRI image with command `fsleyes IMAGENAME.nii.gz`

#### 3. Look for artefacts

Here some artefacts and how they look like:
- 

## Questions

*What if I am not sure on what to look for?* Do this check with a more experienced colleague. You can also ask for an expert opinion from AMI personnel if you think that there are measurement issues with your MRI data.

*The image does not open with fsleyes* OR *dcm2niix is not able to convert the DICOM to NIFTI*. 
There might be a problem related to data corruption of the files, for example the transfer was not successful or other errors related to file storage (e.g. your disk quota is full and some files were trunkated). Please contact AMI personnel so they can verify that the copy of the image on their server is fine.

## Incidental findings

Sometimes when inspecting the MRI images, the brain of the participants that you look at might look different than the typical brain you have seen during your studies. If there are no MRI artefacts, the MRI image might display possible health related issues with the participant's brain such as brain tumors, cavernomas, calcifications, cysts, and other anomalies in the MRI image. In these cases, please follow the procedure for incidental findings that you have outlined in your ethical application. Most likely the procedure involves sending an image to AMI personnell and the responsible medical doctor to ask for their expert opinion. Incidental findings are not rare (1 out of 100) and it is important that the doctor gets in touch with the participants immediately if they want to recommend another MRI measurement at hospital facilities.

It is however important to remember that the images collected with the scanner at AMI cannot be used for medical purposes since the equipment and the sequences use are not exactly the same that you have in a standard hospital MRI scanner. Please let the medical doctor decide how to proceed and they can be in touch with the research subject.

## MEG/EEG data quality assurance

To be done.

