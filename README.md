# Civitai Downloader
Downloads specified models from Civitai, along with metadata and images.

For now it supports downloading one or more models from URLs manually inserted by the user.
I'll add support for downloading favorited models and all models by uploader later.
Next thing coming is command line arguments and a config file.

I don't plan to add functionality to download the entire site, if you want to do that edit the code by yourself.

## Known issues:
- Gifs might be downloaded as JPEGs or other formats

# How to use
**NOT TESTED ON LINUX**

This guide assumes you have basic knowledge on how to run python code and use cmd/powershell. If you don't, please search on youtube first.

- Clone or download this repo.
  - `git clone https://github.com/4zure0/civitai_downloader.git`
  or
  - `git clone https://github.com/zyeternity/better_civitai_downloader.git`
- Make sure you have python installed. Although it might run on other versions, it was made to run on python 3.10. You can check your version with `python --version`
- Install dependencies with pip. To do that navigate to the folder you downloaded this repository and run `python -m pip install -r requirements.txt` on powershell/cmd.
- Run civitai_downloader.py with `python civitai_downloader.py`
- Enter the models you want to downloader and press enter.

This will downloader the models under a folder called "models", in the same directory that your civitai_downloader.py file is located. 

Feel free to contribute to the project. Right now this is a big mess that needs improvements after all :D
If you have any problems or bug reports just open a new issue and I'll check it when I have time.

## Slightly "advanced":
You can change options by editing the code in config.ini
```
# Basic config
[Basic]
#This doesn't work with full paths. It will just change the folder name.(But using full paths worked in my environment --lzyeternity)
models_save_folder=models
#If you want to increase your rate limits on Civitai, get your API token (from account setings) and put it there as a string OR "None"
civitai_token=None

# Metadata Options
[Metadata]
updated_metadata=True
backup_metadata=True

# Models Options
[Models] 
skip_duplicate_models=True
use_subfolder=False

# Image Options
[Image] 
skip_duplicate_images=True
# Most of times corrupted files don't exist on Civitai anymore, but the API still return them when you request the model's metadata
redownload_corrupted=False 
```

