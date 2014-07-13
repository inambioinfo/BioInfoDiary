Install R-base on remote Amazon EC2 server (Ubuntu)
========
## Preparation
  # Connect to remote server

  `$ ssh -X -i ……` # -X is to send screen to local computer
  `$ sudo apt-get install gfortran`
  `$ sudo apt-get install xorg-dev #X11`

If texlive is required, then:

  `$ wget http://mirror.ctan.org/systems/texlive/tlnet/install-tl-unx.tar.gz`
  `$ tar -xf install-tl-unx.tar.gz` # This will install tex by smartly choose your nearest neighbour.
  `$ cd install-tl-20140712`
  `$ sudo makedir /usr/local/texlive`
  `$ sudo chown <your-user> /usr/local/texlive`
  `$ ./install-tl` # takes a while. 

  `$ sudo apt-get install texinfo`
## Install R
R coming with the default source in Ubuntu is very old, and is not good for anything basically, except for archaeology. So it is important to get an up-to-date version of R.  
Answer copied from [StackOverflow](http://stackoverflow.com/questions/16093331/how-to-install-r-version-3-0)

Uninstall old R (if necessary):

  `$ sudo apt-get remove r-base-core`

Then:

  `$ sudo gedit /etc/apt/sources.list`

Add the following to the file:

  `deb http://cran.rstudio.com/bin/linux/ubuntu precise/`

and exit gedit.

Then copy/paste these commands into the command line:

  `$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9`
  `$ sudo add-apt-repository ppa:marutter/rdev`
  `$ sudo apt-get update`
  `$ sudo apt-get upgrade`
  `$ sudo apt-get install r-base`

If you need R studio, then:

  `$ sudo apt-get install libjpeg62`
  `$ wget http://download1.rstudio.org/rstudio-0.98.953-amd64.deb` # check latest R studio package to replace the link.
  `$ sudo dpkg -i rstudio-0.98.953-amd64.deb`

And you are good to go!

To run R:

  `$ R`

To run R studio:

  `$ rstudio`

