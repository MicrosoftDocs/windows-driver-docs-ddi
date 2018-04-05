---
UID: NI:charging.IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
title: IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
author: windows-driver-content
description: This IOCTL is for internal use only.
old-location: battery\ioctl_cad_get_battery_provisioning_status.htm
old-project: battery
ms.assetid: 4E92A629-C080-4C32-8768-D0615F35B161
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS, IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS control code [Battery Devices], battery.ioctl_cad_get_battery_provisioning_status, charging/IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
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
-	IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS
product:
- Windows
targetos: Windows
req.typenames: POWERSOURCEID, *PPOWERSOURCEID
---

# IOCTL_CAD_GET_BATTERY_PROVISIONING_STATUS IOCTL


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

For more information, see [NTSTATUS Values](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/ntstatus-values).



