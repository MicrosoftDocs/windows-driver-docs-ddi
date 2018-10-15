---
UID: NI:hidclass.IOCTL_HID_GET_DRIVER_CONFIG
title: IOCTL_HID_GET_DRIVER_CONFIG
author: windows-driver-content
description: The IOCTL_HID_GET_DRIVER_CONFIG request retrieves the driver configuration.
old-location: hid\ioctl_hid_get_driver_config.htm
tech.root: hid
ms.assetid: F648EF1E-2673-499D-81BF-03B7B2148FA2
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_HID_GET_DRIVER_CONFIG, IOCTL_HID_GET_DRIVER_CONFIG control, IOCTL_HID_GET_DRIVER_CONFIG control code [Human Input Devices], hid.ioctl_hid_get_driver_config, hidclass/IOCTL_HID_GET_DRIVER_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidclass.h
req.include-header: Hidclass.h
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
-	hidclass.h
api_name:
-	IOCTL_HID_GET_DRIVER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_DRIVER_CONFIG IOCTL


## -description


The <b>IOCTL_HID_GET_DRIVER_CONFIG</b> 
   request retrieves the driver configuration.

This IOCTL is reserved for system use.


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



