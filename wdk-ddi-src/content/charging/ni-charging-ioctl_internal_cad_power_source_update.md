---
UID: NI:charging.IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
title: IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: battery\ioctl_internal_cad_power_source_update.htm
old-project: battery
ms.assetid: 9D49DA3A-D19E-4834-B5B4-CEF0F235F954
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE, IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE control code [Battery Devices], battery.ioctl_internal_cad_power_source_update, charging/IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	charging.h
api_name:
-	IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE
product: Windows
targetos: Windows
req.typenames: POWERSOURCEID, *PPOWERSOURCEID
---

# IOCTL_INTERNAL_CAD_POWER_SOURCE_UPDATE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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



