---
UID: NI:hidclass.IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
title: IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_MS_GENRE_DESCRIPTOR request is used for retrieving the genre descriptor for the device.
old-location: hid\ioctl_hid_get_ms_genre_descriptor.htm
tech.root: hid
ms.assetid: C83C6086-369D-41DB-BEB5-33B3A0C1C0AE
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_HID_GET_MS_GENRE_DESCRIPTOR, IOCTL_HID_GET_MS_GENRE_DESCRIPTOR control, IOCTL_HID_GET_MS_GENRE_DESCRIPTOR control code [Human Input Devices], hid.ioctl_hid_get_ms_genre_descriptor, hidclass/IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
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
-	IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_MS_GENRE_DESCRIPTOR IOCTL


## -description


The <b>IOCTL_HID_GET_MS_GENRE_DESCRIPTOR</b> 
   request is used for retrieving the genre descriptor for the device.


## -ioctlparameters




### -input-buffer


       The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. 


### -input-buffer-length




### -output-buffer

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.


### -output-buffer-length

The size of a status code.


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

