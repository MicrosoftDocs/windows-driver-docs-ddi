---
UID: NS:ntddk._CONFIGURATION_INFORMATION
tech.root: kernel
title: CONFIGURATION_INFORMATION
ms.date: 06/27/2023
targetos: Windows
description: Learn more about the CONFIGURATION_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntddk.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.target-type: 
req.typenames: CONFIGURATION_INFORMATION, *PCONFIGURATION_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _CONFIGURATION_INFORMATION
 - PCONFIGURATION_INFORMATION
 - CONFIGURATION_INFORMATION
f1_keywords:
 - _CONFIGURATION_INFORMATION
 - ntddk/_CONFIGURATION_INFORMATION
 - PCONFIGURATION_INFORMATION
 - ntddk/PCONFIGURATION_INFORMATION
 - CONFIGURATION_INFORMATION
 - ntddk/CONFIGURATION_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _CONFIGURATION_INFORMATION
---

## -description

The **CONFIGURATION_INFORMATION** structure contains the overall system device configuration record.

## -struct-fields

### -field DiskCount

Number of hard disks in the system thus far. A driver can use this number to determine the names of new disks. The driver should update this value as it finds new disks.

### -field FloppyCount

Number of floppy disks in the system thus far. A driver can use this number to determine the names of new disks. The driver should update this value as it finds new disks.

### -field CdRomCount

Number of CD-ROM drives in the system thus far. A driver can use this number to determine the names of new drives. The driver should update this value as it finds new drives.

### -field TapeCount

Number of tape drives in the system thus far. A driver can use this number to determine the names of new drives. The driver should update this value as it finds new drives.

### -field ScsiPortCount

Number of SCSI port adapters in the system thus far. A driver can use this number to determine the names of new SCSI port adapters. The driver should update this value as it finds new adapters.

### -field SerialCount

Number of serial devices in the system thus far. A driver can use this number to determine the names of new serial devices. The driver should update this value as it finds new devices.

### -field ParallelCount

Number of parallel devices in the system thus far. A driver can use this number to determine the names of new parallel devices. The driver should update this value as it finds new devices.

### -field AtDiskPrimaryAddressClaimed

Boolean that indicates ownership of the 0x1F0-0x1FF space of the two I/O address spaces used by WD1003-compatible disk controllers.

### -field AtDiskSecondaryAddressClaimed

Boolean that indicates ownership of the 0x170-0x17F space of the two I/O address spaces used by WD1003-compatible disk controllers.

### -field Version

The version of this structure. Set to ```sizeof(CONFIGURATION_INFORMATION)```.

### -field MediumChangerCount

Number of medium changer devices in the system. A driver can use this number to determine the names of new medium changer devices. The driver should update this value as it finds new devices.

## -remarks

**CONFIGURATION_INFORMATION** can be used as follows:

* By drivers that are initializing to determine the number of devices of a particular type that have already been initialized.
* To track whether or not the AtDisk address range has already been claimed.
* By the [**IoGetConfigurationInformation **](nf-ntddk-iogetconfigurationinformation.md) system service to return device type counts.

## -see-also

[**IoGetConfigurationInformation **](nf-ntddk-iogetconfigurationinformation.md) (*ntddk.h*)

[**IoGetConfigurationInformation **](../ntifs/nf-ntifs-iogetconfigurationinformation.md) (*ntifs.h*)
