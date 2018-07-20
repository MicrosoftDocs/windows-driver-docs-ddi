---
UID: NS:wdm._CM_INT13_DRIVE_PARAMETER
title: "_CM_INT13_DRIVE_PARAMETER"
author: windows-driver-content
description: The CM_INT13_DRIVE_PARAMETER structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a disk controller if the system can collect this information during the boot process.
old-location: kernel\cm_int13_drive_parameter.htm
tech.root: kernel
ms.assetid: eee1070f-c821-42bd-a0c9-d429fac6305b
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCM_INT13_DRIVE_PARAMETER, CM_INT13_DRIVE_PARAMETER, CM_INT13_DRIVE_PARAMETER structure [Kernel-Mode Driver Architecture], PCM_INT13_DRIVE_PARAMETER, PCM_INT13_DRIVE_PARAMETER structure pointer [Kernel-Mode Driver Architecture], _CM_INT13_DRIVE_PARAMETER, kernel.cm_int13_drive_parameter, kstruct_a_4d629962-92d1-446d-890b-196893ea37a0.xml, wdm/CM_INT13_DRIVE_PARAMETER, wdm/PCM_INT13_DRIVE_PARAMETER"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	CM_INT13_DRIVE_PARAMETER
product:
- Windows
targetos: Windows
req.typenames: CM_INT13_DRIVE_PARAMETER, *PCM_INT13_DRIVE_PARAMETER
---

# _CM_INT13_DRIVE_PARAMETER structure


## -description


The <b>CM_INT13_DRIVE_PARAMETER</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a disk controller if the system can collect this information during the boot process.


## -struct-fields




### -field DriveSelect

The drive selected value.


### -field MaxCylinders

The maximum number of cylinders.


### -field SectorsPerTrack

The number of sectors per track.


### -field MaxHeads

The maximum number of heads.


### -field NumberDrives

The number of drives. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
 

 

