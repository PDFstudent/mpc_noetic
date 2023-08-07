# mpc_noetic

# How to install Ipopt on x86 environment  

## Install CPPAD & Fortran  
```
sudo apt-get install cppad gfortran  
```
  
## Step by step download the libraries
 
```
cd {$CUSTOM_PATH}/Ipopt-3.12.8  
mkdir build  && cd build  
../configure  
make -j4  
make install  
```

## Copy install files into specific directory 
```
cd CUSTOM_PATH/Ipopt-3.12.8/build  
sudo cp -a include/* /usr/include/.  
sudo cp -a lib/* /usr/lib/.  
```

