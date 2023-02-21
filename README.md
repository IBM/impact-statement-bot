# impact-statement-bot

## Authorship
Primary: Anwesha Mukherjee

Contributors: Vagner Figueredo de Santana, Alex Baria

## Scope
Impact Statement Bot is a chatbot designed to leverage language models to automate providing feedback to researchers on their impact statements according to specific responsible and inclusive objectives. The most recent application is hosted in widget.ipynb though previous forms are also included in teh repository. 

## Independent Use
The environment is prescribed in `environment.yml` and can be replicated for use. Please do not make any direct alterations if given editing permissions. Make pull requests for interest in feature additions and open an issue so it can be reviewed. 

## Remote/Locally Run User Session/Experiment Instructions
You may choose to follow instructions using either [Conda](#using-conda) or a [virtual environment](#using-a-venv-with-pip-only). Conda is heavily recommended and impact statement bot was developed within a conda environment so the dependcies and ordering are exact. At your own risk, you may encounter dependency issues with pip. 

#### OS
All instructions assume you will be running your experiment on a machine with either MacOS or a Linux/Unix OS. You may choose to run your experiments on a Windows machine, however, all following instructions should be adapted to the Windows command prompt. 

### Using Conda
1. Install conda using following process, miniconda should work though anaconda is preferable: https://docs.anaconda.com/anaconda/install/
2. Check if you already of have jupyter installed. If so, note down what versions of jupyter and jupyter-core for future kernel debugging purposes.
3. Git clone the repo whether via github desktop or command: `git clone https://github.com/IBM/impact-statement-bot.git`
4. Enter repo directory: `cd /path/to/impact-statement-bot`
5. Then create conda environment from environment.yml as follows: `conda env create -f environment.yml` This may take time so be patient. Check yes when necessary.
6. Activate conda environment baseline: `conda activate baseline`
7. Do you have git lfs installed and active? If not, [follow all LFS instructions below](#git-lfs-instructions). If so, [jump to Getting the LFS Files](#getting-the-lfs-files). 
8. Run widget app using voila: `voila widget.ipynb`
9. Interact with the widgets for the user session on the open application. 
10. When finished, press done to complete the session and close out of the app. 
11. Data collected as a txt in the user sessions folder will be moved to the box folder. To make them available: `git commit -m "User Session - <Name>"`
12. Then push: `git push`
13. Deactivate conda environment with: `conda deactivate`

#### Debugging Kernel Not Found, HTTP 404: Kernel Does Not Exist, 404 GET /api/kernels/(Kernel does not exist:)
1. Uninstall Jupyter and all it's dependencies from your pip
`pip install pip-autoremove`
`pip-autoremove jupyter -y`
2. If you may also have installed Jupyter via conda:
`conda uninstall notebook`
3. Uninstall and reinstall anaconda
4. Retry steps 4-12 above

### Using a VENV With Pip Only
Note: The instructions assumes python3, you may use the python alias for python3 depending on your machine's python command configuration
Note: You may also need to replace pip with pip3
1. Install virtualenv if you haven't already: `python3 -m pip install --user virtualenv`
2. Create a new virtual environment: `python3 -m venv /path/to/new/virtual/environment/ibvenv`
3. Activate the virtual environment: `source /path/to/new/virtual/environment/ibvenv/bin/activate`
4. Upgrade pip: `python -m pip install -U pip`
5. Git clone the repo whether via github desktop or command: `git clone https://github.com/IBM/impact-statement-bot.git`
6. Enter repo directory: `cd /path/to/impact-statement-bot`
7. Install all needed dependencies from requirements.txt: `pip install -r requirements.txt`
8. Do you have git lfs installed and active? If not, [follow all LFS instructions below](#git-lfs-instructions). If so, [jump to Getting the LFS Files](#getting-the-lfs-files).
9. Run widget app using voila: `voila widget.ipynb`
10. Interact with the widgets for the user session on the open application. 
11. When finished, press done to complete the session and close out of the app. 
12. Data collected as a txt in the user sessions folder will be moved to the box folder. To make them temporarily available: `git commit -m "User Session - <Name>"`
13. Then push: `git push`
14. Terminate your session with the virtual environment, or `deactivate` to keep the session but with a default python interpreter. 

### Git LFS Instructions
You will need git lfs on your machine to be able to pull large files from the repository, namely two custom fine-tuned RoBERTa models used for classification in impact-statement-bot. 
In general, follow instructions at this link: https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage
1. On a Mac, it's easiest by far to install via brew: `brew install git-lfs`
2. Skip to step 6 on the link: `git lfs install`

#### Getting the LFS files
Once you have finished installing git lfs:
1. If you moved directories, return to the impact-statement-bot directory: `cd \path\to\impact-statement-bot` 
2. Pull lfs files as you would a git directory: `git lfs pull`
3. Verify that the files `\path\to\impact-statement-bot\neurips-roberta\use\pytorch_model.bin` and `\path\to\impact-statement-bot\neurips-roberta\mitigate\pytorch_model.bin` exist
4. If they exist, return to [Conda step 8](#using-conda) and [virtual env step 9](#using-a-venv-with-pip-only)


<!-- A notes section is useful for anything that isn't covered in the Usage or Scope. Like what we have below. -->
## Notes

**NOTE: This repository has been configured with the [DCO bot](https://github.com/probot/dco).
When you set up a new repository that uses the Apache license, you should
use the DCO to manage contributions. The DCO bot will help enforce that.
Please contact one of the IBM GH Org stewards.**

<!-- Questions can be useful but optional, this gives you a place to say, "This is how to contact this project maintainers or create PRs -->
If you have any questions or issues you can create a new [issue here][issues].

Pull requests are very welcome! Make sure your patches are well tested.
Ideally create a topic branch for every separate change you make. For
example:

1. Fork the repo
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## License

All source files must include a Copyright and License header. The SPDX license header is 
preferred because it can be easily scanned.

If you would like to see the detailed LICENSE click [here](LICENSE).

```text
#
# Copyright 2020- IBM Inc. All rights reserved
# SPDX-License-Identifier: Apache2.0
#
```

## Questions
Open an issue and reach out. 

[issues]: https://github.com/IBM/repo-template/issues/new
