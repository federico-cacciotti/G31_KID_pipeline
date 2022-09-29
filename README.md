# KID_pipeline package
A pipeline for Kinetic Inductance Detectors data analysis and characterization that I developed during my master thesis and PhD.

# Overview
A short overview of the package is given here. To import the package just include it in your Python code as follows:

```Python
import pipeline as pl
```
Once the package is imported in your code, it automatically checks if all the data directories exist. If it doesn't find one or more data directories, it creates them in the same path of your Python script. At the end of this operation you should have the following directories in your script path:

```sh
anritsu_MS2034B
cosmic_rays
data_logger
noise
picolog
target
target_S21
vna
vna_S21
your_python_script.py
```

- `anritsu_MS2034B` should contain the output files from the Vector Network Analyzer Anritsu MS2034B;
- `cosmic_rays` should contain the output files of cosmic ray events taken using a Tektronix DPO3054 digital oscilloscope;
- `data_logger` should contain the dirfiles coming from the ROACH readout;
- `noise` should contain the extracted noise time streams in `.npy` file format;
- `picolog` should contain the PicoLog output files;
- `target` should contain the target sweep files coming from the ROACH readout;
- `target_S21` should contain the target sweep files converted into `.npy` files for each channel;
- `vna` should contain the VNA sweep files coming from the ROACH readout;
- `vna_S21` should contain the VNA sweep files converted into `.npy` files for each channel.



# `VNA` object

You can open a `VNA` file by defining a `VAN` object as

```Python
vna = pl.VNA.VNA(filename='20220531_04', temperature=270, build_dataset=True)
```
where the optional `temperature` parameter (default is `None`) defines the temperature of the VNA sweep expressed in milli kelvin and the optional `build_dataset` parameter (default is `False`) converts the raw VNA sweep files into `.npy` files by creating a subfolder under the `VNA_S21` directory with the same name of the `filename` parameter.

## Operations with the `VNA` object



# `target` object

You can open a `target` file by defining a `target` object as

```Python
target = pl.Target.Target(filename='20220530_145142', temperature=150, build_dataset=True)
```
where the optional `temperature` parameter (default is `None`) defines the temperature of the target sweep expressed in milli kelvin and the optional `build_dataset` parameter (default is `False`) converts the raw target sweep files into `.npy` files by creating a subfolder under the `target_S21` directory with the same name of the `filename` parameter.

## Operations with the `target` object
