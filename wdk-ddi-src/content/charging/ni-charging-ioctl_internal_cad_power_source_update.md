---
UID: NI:charging.IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
title: IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: battery\ioctl_internal_cad_power_source_update.htm
old-project: battery
ms.assetid: 9D49DA3A-D19E-4834-B5B4-CEF0F235F954
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: battery.ioctl_internal_cad_power_source_update, IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE control code [Battery Devices], IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE, charging/IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: charging.h
req.include-header: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	charging.h
apiname:
-	IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
product: Windows
targetos: Windows
req.typenames: "*PPOWERSOURCEID, POWERSOURCEID"
---

# IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This IOCTL is for internal use only.


## -ioctlparameters




### -input-buffer


<text></text>



### -input-buffer-length


<text></text>



### -output-buffer


<text></text>



### -output-buffer-length


<text></text>



### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block


Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.
Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [XREF-LINK:NTSTATUS Values].


