---
UID: NS:wdm._CM_FLOPPY_DEVICE_DATA
title: _CM_FLOPPY_DEVICE_DATA (wdm.h)
description: The CM_FLOPPY_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process.
old-location: kernel\cm_floppy_device_data.htm
tech.root: kernel
ms.assetid: 0ef0d242-4ed6-4c48-85b8-0fc87d3fe39b
ms.date: 04/30/2018
ms.keywords: "*PCM_FLOPPY_DEVICE_DATA, CM_FLOPPY_DEVICE_DATA, CM_FLOPPY_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_FLOPPY_DEVICE_DATA, PCM_FLOPPY_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_FLOPPY_DEVICE_DATA, kernel.cm_floppy_device_data, kstruct_a_7ec8badb-4d88-479e-b0dc-ce88660b8449.xml, wdm/CM_FLOPPY_DEVICE_DATA, wdm/PCM_FLOPPY_DEVICE_DATA"
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_FLOPPY_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: CM_FLOPPY_DEVICE_DATA, *PCM_FLOPPY_DEVICE_DATA
---

# _CM_FLOPPY_DEVICE_DATA structure


## -description


The <b>CM_FLOPPY_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process.


## -struct-fields




### -field Version

The version number of this structure.


### -field Revision

The revision of this structure.


### -field Size

The floppy disk density size.


### -field MaxDensity

The maximum density.


### -field MountDensity

The mount density.


### -field StepRateHeadUnloadTime

The step rate head unload time in milliseconds.


### -field HeadLoadTime

The head load time in milliseconds.


### -field MotorOffTime

The motor off time in seconds.


### -field SectorLengthCode

Indicates the sector size as an exponent in the formula ((2**<i>code</i>) * 128). 


### -field SectorPerTrack

The number of sectors per track.


### -field ReadWriteGapLength

The read/write gap length, in bytes.


### -field DataTransferLength

The data transfer length, in bytes, not including the synchronization field.


### -field FormatGapLength

The format gap length, in bytes.


### -field FormatFillCharacter

The format fill character.


### -field HeadSettleTime

The head settle time in milliseconds.


### -field MotorSettleTime

The motor settle time in milliseconds.


### -field MaximumTrackValue

The maximum track number on the media. Track numbers are zero-based values.


### -field DataTransferRate

The value written to the Datarate register before accessing the media. 


## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
 

 

