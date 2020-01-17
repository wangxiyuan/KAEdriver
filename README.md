# Kunpeng Acceleration Engine Driver

- [Introduction](#introduction)
- [License](#license)
- [Requirements](#requirements)
- [Installation Instructions](#installation-instructions)
- [More Information](#more information)
- [Copyright](#Copyright)

## Introduction

It is the driver for the Kunpeng Acceleration Engine，which is a new technology within Hisilicon Kunpeng 920 processors，provides a hardware-enabled foundation for security, authentication, and compression. It significantly increases the performance across cloud, networking, big data, and storage applications and  platforms.  For more information,  please see the following location at:

<https://github.com/kunpengcompute/kunpeng_kae>

## License
The Licensing of the files within this project is split as follows:

The kernel-space KAE driver is under the [SPDX-GPL-2.0](https://opensource.org/licenses/GPL-2.0 ). Please see the LICENSE file in the top level of `kae_driver`.

The user-space KAE driver is under the [APACHE LICENSE, VERSION 2.0](https://www.apache.org/licenses/LICENSE-2.0 ). Please see the LICENSE file in the top level of `warpdrive`.

## Requirements

- CPU: Kunpeng 920 
- Operating System: 
  - CentOS 7.6  4.14.0-115.el7a.0.1.aarch64 version
  - SuSE 15.1 4.12.14-195-default arch64 version
  - NeoKylin 7.6 4.14.0-115.5.1.el7a.06.aarch64 version
  - EulerOS 2.8 4.19.36-vhulk1907.1.0.h410.eulerosv2r8.aarch64 version

## Installation Instructions

Download the release version of Kunpeng Accelerator Engine Driver from:

```
<https://github.com/kunpengcompute/KAEdriver>
```

Note: To build the Kunpeng Accelerator Engine Driver, install the `kernel-devel` package first.

Firstly, install the accelerator driver:

```
cd kae_driver
make
make install
modprobe uacce
modprobe hisi_qm
modprobe hisi_sec2
modprobe hisi_hpre
modprobe hisi_zip
modprobe hisi_rde
```

Check the accelerator driver has been loaded successfully by running the `lsmod` command. 

`uacce.ko, hisi_qm.ko, sgl.ko, hisi_sec2.ko, hisi_hpre.ko, hisi_zip.ko` should be in the list. 

Secondly, install the warpdrive:

```
cd warpdrive
sh autogen.sh 
./configure 
make 
make install
```
Check the accelerator driver has been loaded successfully by running the `ls -al /usr/local/lib` command. `libwd.so` should be in the list. 
## More Information

For further assistance, contact Huawei Support at:

<https://support.huawei.com>
<https://www.huaweicloud.com/kunpeng/software/accelerator.html>

## Copyright

Copyright © 2018 Huawei Corporation. All rights reserved.