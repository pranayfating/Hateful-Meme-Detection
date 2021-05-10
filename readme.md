# Hateful Meme Detection

This is a repository for our work on Facebook's Hateful Meme challenge.

## Prerequisites

Install MMF following the [installation docs](https://mmf.sh/docs) .

## Dataset

To acquire the data, you will need to register at DrivenData's Hateful Memes Competition and download data from the challenge's [download page](https://www.drivendata.org/competitions/64/hateful-memes/). MMF won't be able to automatically download the data since you manually need to agree to the licensing terms. Follow the steps below to convert data into MMF format.

Dataset will be protected with a password, which you can get from the same download page.

1. Download the zip file with data from DrivenData at location x.
2. Note the password from the data download page at DrivenData as y
3. Run ```mmf_convert_hm --zip_file=x --password=y``` where you replace x with the location of your zip file and y with the password you noted.
4. The Previous command will unzip and format your files into MMF format.

## Experiments

### ResNeXt+BERT+TF

1. Upload all the contents of the "Drive" folder to your drive.
2. Change the appropriate paths of local files as given in the code.
3. Run ```resnext101_32x8d.ipynb```. This will save ```resnext101_32x8d.tar``` file on your drive in ```saved_model_checkpoints``` folder.
4. Run ```BERT.ipynb```. This will save ```BERT.tar``` file on your drive in ```saved_model_checkpoints``` folder.
5. Now in ```BERT+ResNeXt+TF.ipynb``` change the paths of the above two ```tar``` files and also the dataset files.

### VisualBERT+TF

1. First download the mmf library from the commands given in the code.
2. Change the following files with files given in the above ```MMF``` folder.
    ```
    1. defaults.yaml   -    mmf/configs/datasets/hateful_memes/defaults.yaml
    2. dataset.py   -   mmf/datasets/builders/hateful_memes/dataset.py
    3. defaults.yaml    -   projects/visual_bert/configs/hateful_memes/defaults.yaml
    4. visual_bert.py    -   mmf/models/visual_bert.py```
3. Run the ```VisualBERT+TF.ipynb``` file.
