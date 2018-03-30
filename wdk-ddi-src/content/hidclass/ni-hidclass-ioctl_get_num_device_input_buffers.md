---
UID: NI:hidclass.IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
title: IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
author: windows-driver-content
description: The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a top-level collection.
old-location: hid\ioctl_get_num_device_input_buffers.htm
old-project: hid
ms.assetid: 3a0a8fa3-2d23-412c-ad54-d8ba5809cbe4
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS, IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS control code [Human Input Devices], hid.ioctl_get_num_device_input_buffers, hidclass/IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS, hidioreq_4d76e323-5cc1-40d2-aa56-ca5427f15e6f.xml
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
-	IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS IOCTL


## -description


The IOCTL_GET_NUM_DEVICE_INPUT_BUFFERS request obtains the size of the input report queue for a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. 

The input report queue is implemented as a ring buffer. If a collection transmits data to the HID class driver faster than the input reports are read, reports can be lost. The size of the input report queue can be adjusted using <a href="https://msdn.microsoft.com/library/windows/hardware/ff542087">IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS</a>. 

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(ULONG). 


### -input-buffer-length

The size of the buffer is <b>sizeof</b>(ULONG). 


### -output-buffer

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the size of the report input queue. 


### -output-buffer-length

The size of the buffer is <b>sizeof</b>(ULONG). 


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to <b>sizeof</b>(ULONG) if the size of the report input queue is successfully retrieved. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539686">HidD_SetNumInputBuffers</a>
 

 

