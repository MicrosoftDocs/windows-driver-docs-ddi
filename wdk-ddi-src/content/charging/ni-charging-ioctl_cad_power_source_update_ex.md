---
UID: NI:charging.IOCTL_CAD_POWER_SOURCE_UPDATE_EX
title: IOCTL_CAD_POWER_SOURCE_UPDATE_EX (charging.h)
description: This IOCTL is for internal use only.
old-location: battery\ioctl_cad_power_source_update_ex.htm
tech.root: battery
ms.assetid: 8D582EF9-B9D1-498B-AE20-337F3A33250C
ms.date: 02/15/2018
ms.keywords: IOCTL_CAD_POWER_SOURCE_UPDATE_EX, IOCTL_CAD_POWER_SOURCE_UPDATE_EX control, IOCTL_CAD_POWER_SOURCE_UPDATE_EX control code [Battery Devices], battery.ioctl_cad_power_source_update_ex, charging/IOCTL_CAD_POWER_SOURCE_UPDATE_EX
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
-	IOCTL_CAD_POWER_SOURCE_UPDATE_EX
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CAD_POWER_SOURCE_UPDATE_EX IOCTL


## -description


This IOCTL is for internal use only.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



