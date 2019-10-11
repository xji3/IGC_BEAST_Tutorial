# IGC_BEAST_Tutorial
Explains how to use gene_conversion branch on BEAST

### 0. Getting BEAST and BEAGLE
We are going to use the development branch of both BEAST and BEAGLE.  Assuming you are using mac / linux, the following commands should get you the right versions.

#### 0.1 BEAGLE
Please follow the [BEAGLE installation instructions](https://github.com/beagle-dev/beagle-lib).
But get the `hmc-clock` branch.

For mac users, the following commands will compile the CPU version the CPU version.
Follow the instructions if you need to install any software.

```
xcode-select --install
brew install libtool autoconf automake
git clone -b hmc-clock https://github.com/beagle-dev/beagle-lib.git
cd beagle-lib
./autogen.sh
./configure --without-opencl --without-cuda
sudo make install
```

The libraries are installed into `/usr/local/lib`.
You can find them by `ls /usr/local/lib/*beagle*`.

#### 0.2 BEAST
The following commands will compile the `gene_conversion` branch of BEAST.
You may need to install ant by `brew install ant` through [Homebrew](https://brew.sh/).

```
git clone -b gene_conversion https://github.com/beast-dev/beast-mcmc.git
cd beast-mcmc
ant
```

This will compile the `jar` files under `beast-mcmc/build/dist/` where you can find `beast.jar`, `beauti.jar` and `trace.jar`.

#### 1 Set up the IGC model in BEAST xml file
The example [xml file](xmls/first_example.xml) sets up the HKY+IGC model with single IGC parameter for the YEAST ribosomal protein coding genes `YLR406C` and `YDL075W`.

Before runnign the xml file, let's look at the command line options for running BEAST.

```
cd where_you_want_to_run
java -jar -Djava.library.path=/usr/local/lib where_beast_is_git_cloned/beast-mcmc/build/dist/beast.jar -help
```

To run the example xml file, try the following lines

```
cd where_you_want_to_save_output
java -jar -Djava.library.path=/usr/local/lib where_beast_is_git_cloned/beast-mcmc/build/dist/beast.jar -seed 666 -overwrite where_xml_file_is_stored/first_example.xml
```

to be continued...


