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

to be continued...


