---
UID: NI:hidclass.IOCTL_HID_FLUSH_QUEUE
title: IOCTL_HID_FLUSH_QUEUE (hidclass.h)
description: The IOCTL_HID_FLUSH_QUEUE request dequeues all of the unparsed input reports from a top-level collection's input report queue.
old-location: hid\ioctl_hid_flush_queue.htm
tech.root: hid
ms.assetid: 97914eb2-18fd-4b7b-8dcd-475c4d98927c
ms.date: 04/30/2018
keywords: ["IOCTL_HID_FLUSH_QUEUE IOCTL"]
ms.keywords: IOCTL_HID_FLUSH_QUEUE, IOCTL_HID_FLUSH_QUEUE control, IOCTL_HID_FLUSH_QUEUE control code [Human Input Devices], hid.ioctl_hid_flush_queue, hidclass/IOCTL_HID_FLUSH_QUEUE, hidioreq_d7b2ccb0-76c8-4aa7-9d05-b8226106baa6.xml
f1_keywords:
 - "hidclass/IOCTL_HID_FLUSH_QUEUE"
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
- IOCTL_HID_FLUSH_QUEUE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_FLUSH_QUEUE IOCTL


## -description


The IOCTL_HID_FLUSH_QUEUE request dequeues all of the unparsed input reports from a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> input report queue. 

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer


       None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the <b>Status</b> member of <b>Irp->IoStatus</b> to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_flushqueue">HidD_FlushQueue</a>
 

 

