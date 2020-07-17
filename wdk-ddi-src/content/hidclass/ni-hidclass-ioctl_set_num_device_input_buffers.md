---
UID: NI:hidclass.IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS
title: IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS (hidclass.h)
description: The IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request sets the number of buffers for the input report queue of a top-level collection.
old-location: hid\ioctl_set_num_device_input_buffers.htm
tech.root: hid
ms.assetid: a44f9d57-473c-45ed-94e3-db339c6d2296
ms.date: 04/30/2018
keywords: ["IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS IOCTL"]
ms.keywords: IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS, IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS control, IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS control code [Human Input Devices], hid.ioctl_set_num_device_input_buffers, hidclass/IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS, hidioreq_2fe1c0f7-6867-4924-a76f-b7970ebb1201.xml
f1_keywords:
 - "hidclass/IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS"
 - "IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hidclass.h
api_name:
- IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS IOCTL


## -description


The IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request sets the number of buffers for the input report queue of a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection</a>. 

Each input report queue is implemented as a ring buffer. If a collection transmits data to the HID class driver faster than the driver can read it, some of the data may be lost. To prevent this type of loss, you can use an IOCTL_SET_NUM_DEVICE_INPUT_BUFFERS request to adjust the number of buffers that the input report queue contains. The HID class driver requires a minimum of two input buffers. On Windows 2000, the maximum number of input buffers that the HID class driver supports is 200, and on Windows XP and later, the maximum number of input buffers that the HID class driver supports is 512. The default number of input buffers is 32.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Irp->AssociatedIrp.SystemBuffer</b> points to a ULONG-sized input buffer that receives the new number of buffers for the input report queue.

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP contains the size, in bytes, of the input bufferat <b>Irp->AssociatedIrp.SystemBuffer</b>. This size must be <b>sizeof</b>(ULONG).


### -input-buffer-length

The size of a ULONG.


### -output-buffer


       None.


### -output-buffer-length


       None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request succeeds, the HID class driver sets the <b>Status</b> field of <b>Irp->IoStatus</b> to STATUS_SUCCESS; otherwise, it sets the <b>Status</b> field to an appropriate NTSTATUS error code.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getnuminputbuffers">HidD_GetNumInputBuffers</a>
 

 

