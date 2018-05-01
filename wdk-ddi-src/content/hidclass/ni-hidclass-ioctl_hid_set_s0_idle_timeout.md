---
UID: NI:hidclass.IOCTL_HID_SET_S0_IDLE_TIMEOUT
title: IOCTL_HID_SET_S0_IDLE_TIMEOUT
author: windows-driver-content
description: The IOCTL_HID_SET_S0_IDLE_TIMEOUT request is used by a client to inform the HID class driver about the client's preferred idle timeout value.
old-location: hid\ioctl_hid_set_s0_idle_timeout.htm
old-project: hid
ms.assetid: 9372E6D5-0E0B-4916-929D-73532FB6A5D6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_SET_S0_IDLE_TIMEOUT, IOCTL_HID_SET_S0_IDLE_TIMEOUT control, IOCTL_HID_SET_S0_IDLE_TIMEOUT control code [Human Input Devices], hid.ioctl_hid_set_s0_idle_timeout, hidclass/IOCTL_HID_SET_S0_IDLE_TIMEOUT
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
-	IOCTL_HID_SET_S0_IDLE_TIMEOUT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_SET_S0_IDLE_TIMEOUT IOCTL


## -description


The <b>IOCTL_HID_SET_S0_IDLE_TIMEOUT</b> 
   request is used by a client to inform the HID class driver about the client's preferred idle timeout value.

When the client sets this value to zero (0), it informs the HID class driver that the preferred idle timeout value is no longer valid. In this case, the HID class driver will start to use the default idle timeout value.


## -ioctlparameters




### -input-buffer


       The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member specifies the size, in bytes, of a requester-allocated output buffer. 


### -input-buffer-length

This is a buffer of size ULONG.


### -output-buffer

The <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> member is a pointer to the requestor-allocated buffer that the client uses to return the idle timeout value.


### -output-buffer-length




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/using-ntstatus-values">NTSTATUS</a> code.

