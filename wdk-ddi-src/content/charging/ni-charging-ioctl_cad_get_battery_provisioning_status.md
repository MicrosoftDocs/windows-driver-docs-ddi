---
UID: NI:charging.IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
title: IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS (charging.h)
description: This IOCTL is for internal use only.
old-location: battery\ioctl_cad_get_battery_provisioning_status.htm
tech.root: battery
ms.assetid: 4E92A629-C080-4C32-8768-D0615F35B161
ms.date: 02/15/2018
ms.keywords: IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS, IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS control, IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS control code [Battery Devices], battery.ioctl_cad_get_battery_provisioning_status, charging/IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
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
-	IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS IOCTL


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



