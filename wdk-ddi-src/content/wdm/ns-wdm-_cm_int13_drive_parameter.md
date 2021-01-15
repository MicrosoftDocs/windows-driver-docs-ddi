---
UID: NS:wdm._CM_INT13_DRIVE_PARAMETER
title: _CM_INT13_DRIVE_PARAMETER (wdm.h)
description: The CM_INT13_DRIVE_PARAMETER structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a disk controller if the system can collect this information during the boot process.
old-location: kernel\cm_int13_drive_parameter.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["CM_INT13_DRIVE_PARAMETER structure"]
ms.keywords: "*PCM_INT13_DRIVE_PARAMETER, CM_INT13_DRIVE_PARAMETER, CM_INT13_DRIVE_PARAMETER structure [Kernel-Mode Driver Architecture], PCM_INT13_DRIVE_PARAMETER, PCM_INT13_DRIVE_PARAMETER structure pointer [Kernel-Mode Driver Architecture], _CM_INT13_DRIVE_PARAMETER, kernel.cm_int13_drive_parameter, kstruct_a_4d629962-92d1-446d-890b-196893ea37a0.xml, wdm/CM_INT13_DRIVE_PARAMETER, wdm/PCM_INT13_DRIVE_PARAMETER"
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
targetos: Windows
req.typenames: CM_INT13_DRIVE_PARAMETER, *PCM_INT13_DRIVE_PARAMETER
f1_keywords:
 - _CM_INT13_DRIVE_PARAMETER
 - wdm/_CM_INT13_DRIVE_PARAMETER
 - PCM_INT13_DRIVE_PARAMETER
 - wdm/PCM_INT13_DRIVE_PARAMETER
 - CM_INT13_DRIVE_PARAMETER
 - wdm/CM_INT13_DRIVE_PARAMETER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _CM_INT13_DRIVE_PARAMETER
 - PCM_INT13_DRIVE_PARAMETER
 - CM_INT13_DRIVE_PARAMETER
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

<a href="/windows-hardware/drivers/kernel/mmcreatemdl">IoQueryDeviceDescription</a>



<a href="/windows-hardware/drivers/kernel/mmcreatemdl">IoReportResourceUsage</a>

