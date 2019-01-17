---
UID: NI:hidclass.IOCTL_HID_GET_POLL_FREQUENCY_MSEC
title: IOCTL_HID_GET_POLL_FREQUENCY_MSEC
description: The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a top-level collection.
old-location: hid\ioctl_hid_get_poll_frequency_msec.htm
tech.root: hid
ms.assetid: 602dc6ac-89cc-4feb-9cef-5226c8abb085
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_GET_POLL_FREQUENCY_MSEC, IOCTL_HID_GET_POLL_FREQUENCY_MSEC control, IOCTL_HID_GET_POLL_FREQUENCY_MSEC control code [Human Input Devices], hid.ioctl_hid_get_poll_frequency_msec, hidclass/IOCTL_HID_GET_POLL_FREQUENCY_MSEC, hidioreq_e0cd09b6-f27f-4a30-918d-c67c2b52da9d.xml
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
-	IOCTL_HID_GET_POLL_FREQUENCY_MSEC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_POLL_FREQUENCY_MSEC IOCTL


## -description


The IOCTL_HID_GET_POLL_FREQUENCY_MSEC request obtains the current polling frequency, in milliseconds, of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be &gt;= <b>sizeof</b>(ULONG). 


### -input-buffer-length

Greater than or equal to <b>sizeof</b>(ULONG). 


### -output-buffer

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the polling frequency. 


### -output-buffer-length




### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to <b>sizeof</b>(ULONG) if the polling frequency is successfully retrieved. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541216">IOCTL_HID_SET_POLL_FREQUENCY_MSEC</a>
 

 

