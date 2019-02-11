<h1> Openframe Installation </h1>

<h3> 1. Software requirements </h3>

- OS
    - CentOS 7.6

- Installing Software
    - tibero6-bin-FS06_CS_1709-linux64-155223-opt-20180621210229
    - jeus70_unix_generic_en fix#4        
    - OpenFrame_COBOL4_409_Linux_x86_64
    - OpenFrame_PLI3_427_Linux_x86_64
    - OpenFrame_ASM4_474_Linux_x86_64
    - OpenFrame_Base7_Fix3_Linux_x86_64
    - OpenFrame_Batch7_Fix3_MVS_Linux_x86_64
    - OpenFrame_GW_7_0_1_Generic
    - OpenFrame_Manager7_Generic
    - OpenFrame_Miner7_0_Generic
    - OpenFrame_OSC7_Fix3_Linux_x86_64
    - OpenFrame_Studio7_Linux_X86_64
    - OpenFrame_Tacf7_Fix3_Linux_x86_64
    - ProTrieve2_1_Linux_x86_64
    - prosort-bin-prosort_2sp3-linux64-2164-opt

- Property Files
    - base.properties
    - batch.properties
    - osc.properties
    - tacf.properties

- Shell Script
    - dbclear.sh

<h3> 2. Installing Tibero </h3>
- yum update & install

```
sudo yum update;
sudo yum install gcc gcc-c++ libgcc libstdc++ libstdc++-devel compat-libstdc++-33 libaio libaio-devel;
```

```
tbsql sys // login to root user
SQL> CREATE USER tibero IDENTIFIED BY 'tmax';
SQL> GRANT ALL PRIVILEGES TO tibero;
```

<h3> 3. Installing JEUS </h3>
- erase all the java already installed
    - yum remove java*
- download jdk from oracle and install 
    - https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
- run the installer
    - chmod 775 jeus70_unix_generic_en.bin
    - ./jeus70_unix_generic_en.bin -i console

<h3> 4. Installing Openframe </h3>

- License
    - Installer/license/Openframe
- Base
    - ./install-file -f property-file
- Batch
    - ./install-file -f property-file
    - batchinit create BASE_ODBC -t OFM_REPOSITORY
- OSC
    - ./install-file -f property-file
    - osctdlinit region-name

<h3> Appendix </h3>
- How to get test license
    - https://technet.tmaxsoft.com => Demo license
- How to download products
    - Get Official: https://technet.tmaxsoft.com => Downloads
    - Get Latest: https://ims.tmaxsoft.com => Search Issues => Binary Request
