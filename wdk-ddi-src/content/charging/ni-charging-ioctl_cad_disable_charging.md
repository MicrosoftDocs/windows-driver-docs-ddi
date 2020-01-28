---
UID: NI:charging.IOCTL_CAD_DISABLE_CHARGING
title: IOCTL_CAD_DISABLE_CHARGING (charging.h)
description: This IOCTL is for internal use only.
old-location: battery\ioctl_cad_disable_charging.htm
tech.root: battery
ms.assetid: 51E91097-7315-489A-8C07-0946481BF573
ms.date: 02/15/2018
ms.keywords: IOCTL_CAD_DISABLE_CHARGING, IOCTL_CAD_DISABLE_CHARGING control, IOCTL_CAD_DISABLE_CHARGING control code [Battery Devices], battery.ioctl_cad_disable_charging, charging/IOCTL_CAD_DISABLE_CHARGING
f1_keywords:
 - "charging/IOCTL_CAD_DISABLE_CHARGING"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- charging.h
api_name:
- IOCTL_CAD_DISABLE_CHARGING
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CAD_DISABLE_CHARGING IOCTL


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



