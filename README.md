# vespa-vm
Virtual machine (VM) with a working version of the <a href="https://github.com/timothydmorton/VESPA">vespa</a> exoplanet statistical validation code. Please see the <a href="https://github.com/timothydmorton/VESPA">vespa code</a> and <a href="https://vespa.readthedocs.io/en/latest/">documentation</a> for more information about using the code.

## Acknowledgements
If you make use of this VM for your research, please cite the original <a href="https://ui.adsabs.harvard.edu/abs/2012ApJ...761....6M/abstract">vespa paper and software</a>, provide a link to this page, and include this or a similar acknowledgement in your work:
*This work made use of a virtual machine provided and maintained by Kevin Hardegree-Ullman to run the vespa code.*

## Installing the VM
- Download the VM image <a href="https://www.dropbox.com/s/hbmmz54wys0268l/vespa.ova?dl=0">here</a>. The file is 17GB, so it might take a while depending on your internet connection.
- Download, install, and open <a href="https://www.virtualbox.org/wiki/Downloads">Oracle VM VirtualBox</a>.
- Select *Import Appliance* from the *File* menu.
- Choose the *vespa.ova* image file to import and click *Next*.
- Edit CPU to ~1/2 the number of cores your computer has (4 is usually a good number if you're unsure).
- Edit RAM to ~1/2 the memory your computer has (most newer computer have at least 8GB, so 4096MB in that case).
- Click *Import*.
- Select *vespa* in the VirtualBox Manager and click *Start*.

## Optimizing VM
- Once the VM is started, in the menu, select *Devices* and click *Insert Guest Additions CD image...*
- Click *Run.*
- Type the root password *vespa* and click *Authenticate*.
- Press *Enter* once the software is installed and reboot VM (top right, *Power Off*, *Restart*).
- Once rebooted, again select *Devices*, *Drag and Drop*, *Bidirectional*. This will enable you to drag and drop files between your machine and the VM.

## Running the vespa example
- Open the terminal (icon in top left corner).
```console
(base) vespa@vespa-vb:~$ conda activate vespa-env
(vespa-env) vespa@vespa-vb:~$ cd Python/vespa/kep22
(vespa-env) vespa@vespa-vb:~$ ls
```
- There are three files, fpp.ini, star.ini, and transit.txt.
```console
(vespa-env) vespa@vespa-vb:~$ starfit --all
```
- This step will take a while.
```console
(vespa-env) vespa@vespa-vb:~$ calcfpp
```
- This step will take a shorter while.
- Your output files will be stored in */home/vespa/Python/vespa/kep22/*.
