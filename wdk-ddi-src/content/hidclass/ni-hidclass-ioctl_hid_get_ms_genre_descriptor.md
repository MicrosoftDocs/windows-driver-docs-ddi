---
UID: NI:hidclass.IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
title: IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_HID_GET_MS_GENRE_DESCRIPTOR request is used for retrieving the genre descriptor for the device.
old-location: hid\ioctl_hid_get_ms_genre_descriptor.htm
old-project: hid
ms.assetid: C83C6086-369D-41DB-BEB5-33B3A0C1C0AE
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hid.ioctl_hid_get_ms_genre_descriptor, IOCTL_HID_GET_MS_GENRE_DESCRIPTOR control code [Human Input Devices], IOCTL_HID_GET_MS_GENRE_DESCRIPTOR, hidclass/IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	hidclass.h
apiname: 
-	IOCTL_HID_GET_MS_GENRE_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: *PHDAUDIO_STREAM_FORMAT, HDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_MS_GENRE_DESCRIPTOR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

