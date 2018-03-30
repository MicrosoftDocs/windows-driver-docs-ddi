---
UID: NS:wdm._CM_SCSI_DEVICE_DATA
title: "_CM_SCSI_DEVICE_DATA"
author: windows-driver-content
description: The CM_SCSI_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process.
old-location: kernel\cm_scsi_device_data.htm
old-project: kernel
ms.assetid: 5cb213c9-24c8-456a-a868-87f1577a8d44
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCM_SCSI_DEVICE_DATA, CM_SCSI_DEVICE_DATA, CM_SCSI_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_SCSI_DEVICE_DATA, PCM_SCSI_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_SCSI_DEVICE_DATA, kernel.cm_scsi_device_data, kstruct_a_af6c0c9a-2191-45f9-ba0f-20c54a202e0a.xml, wdm/CM_SCSI_DEVICE_DATA, wdm/PCM_SCSI_DEVICE_DATA"
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_SCSI_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: CM_SCSI_DEVICE_DATA, *PCM_SCSI_DEVICE_DATA
req.product: Windows 10 or later.
---

# _CM_SCSI_DEVICE_DATA structure


## -description


The <b>CM_SCSI_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process.


## -struct-fields




### -field Version

The version number of this structure.


### -field Revision

The revision for this structure.


### -field HostIdentifier

The SCSI bus identifier used by the ARC firmware. 


## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>
 

 

