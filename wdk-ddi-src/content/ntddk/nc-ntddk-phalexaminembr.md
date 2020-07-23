---
UID: NC:ntddk.pHalExamineMBR
title: pHalExamineMBR (ntddk.h)
description: The HalExamineMBR routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller.
old-location: kernel\halexaminembr.htm
tech.root: kernel
ms.assetid: 6db72f2c-af24-4807-b90b-65dc2b309dc7
ms.date: 04/30/2018
keywords: ["pHalExamineMBR callback function"]
ms.keywords: HalExamineMBR, HalExamineMBR callback function [Kernel-Mode Driver Architecture], k103_86ff3079-34b8-4200-a0e9-88c921579b3f.xml, kernel.halexaminembr, ntddk/HalExamineMBR, pHalExamineMBR, pHalExamineMBR callback
f1_keywords:
 - "ntddk/HalExamineMBR"
 - "HalExamineMBR"
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Ntddk.h
api_name:
- HalExamineMBR
targetos: Windows
req.typenames: 
---

# pHalExamineMBR callback function


## -description


The <b>HalExamineMBR</b> routine reads the master boot record (MBR) of a disk and returns data from the MBR if the MBR is of the type specified by the caller.


## -parameters




### -param DeviceObject [in]

A pointer to the device object for the device being examined.


### -param SectorSize [in]

The minimum number of bytes that an I/O operation can fetch from the device being examined. If this value is less than 512, <b>HalExamineMBR</b> reads 512 bytes to ensure that it reads an entire partition table.


### -param MBRTypeIdentifier [in]

MBR partition type identifier. This parameter specifies the type of MBR that may be on the disk. For more information, see Remarks.


### -param Buffer [out]

A pointer to a location to which <b>HalExamineMBR</b> writes a pointer to a buffer that contains data from the MBR. The layout of the buffer depends on the MBR partition type. <b>HalExamineMBR</b> allocates the storage for this buffer. The caller must deallocate this buffer as soon as possible by calling the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> routine.

<b>HalExamineMBR</b> sets *<i>Buffer</i> = <b>NULL</b> if the MBR partition type of the disk does not match that specified by <i>MBRTypeIdentifier</i> or if there is an error.


## -remarks



For a list of system-defined MBR partition type identifiers, see the table in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>. These identifiers are defined in the Ntdddisk.h header file.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information">PARTITION_INFORMATION</a>
 

 

