---
UID: NS:wdm._CM_SCSI_DEVICE_DATA
title: "_CM_SCSI_DEVICE_DATA"
author: windows-driver-content
description: The CM_SCSI_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process.
old-location: kernel\cm_scsi_device_data.htm
old-project: kernel
ms.assetid: 5cb213c9-24c8-456a-a868-87f1577a8d44
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PCM_SCSI_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_SCSI_DEVICE_DATA, kstruct_a_af6c0c9a-2191-45f9-ba0f-20c54a202e0a.xml, CM_SCSI_DEVICE_DATA, PCM_SCSI_DEVICE_DATA, CM_SCSI_DEVICE_DATA structure [Kernel-Mode Driver Architecture], kernel.cm_scsi_device_data, wdm/PCM_SCSI_DEVICE_DATA, wdm/CM_SCSI_DEVICE_DATA, *PCM_SCSI_DEVICE_DATA
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	CM_SCSI_DEVICE_DATA
product: Windows
targetos: Windows
req.typenames: CM_SCSI_DEVICE_DATA, *PCM_SCSI_DEVICE_DATA
req.product: Windows 10 or later.
---

# _CM_SCSI_DEVICE_DATA structure


## -description


The <b>CM_SCSI_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a SCSI HBA if the system can collect this information during the boot process.


## -syntax


````
typedef struct _CM_SCSI_DEVICE_DATA {
  USHORT Version;
  USHORT Revision;
  UCHAR  HostIdentifier;
} CM_SCSI_DEVICE_DATA, *PCM_SCSI_DEVICE_DATA;
````


## -struct-fields




### -field Version

The version number of this structure.


### -field Revision

The revision for this structure.


### -field HostIdentifier

The SCSI bus identifier used by the ARC firmware. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>



<a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CM_SCSI_DEVICE_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

