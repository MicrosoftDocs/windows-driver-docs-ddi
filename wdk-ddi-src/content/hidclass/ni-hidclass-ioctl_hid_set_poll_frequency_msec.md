---
UID: NI:hidclass.IOCTL_HID_SET_POLL_FREQUENCY_MSEC
title: IOCTL_HID_SET_POLL_FREQUENCY_MSEC (hidclass.h)
description: The IOCTL_HID_SET_POLL_FREQUENCY_MSEC request sets the polling frequency, in milliseconds, for a top-level collection.
old-location: hid\ioctl_hid_set_poll_frequency_msec.htm
tech.root: hid
ms.assetid: 308c07da-8528-4219-ae48-5d20438a183c
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_SET_POLL_FREQUENCY_MSEC, IOCTL_HID_SET_POLL_FREQUENCY_MSEC control, IOCTL_HID_SET_POLL_FREQUENCY_MSEC control code [Human Input Devices], hid.ioctl_hid_set_poll_frequency_msec, hidclass/IOCTL_HID_SET_POLL_FREQUENCY_MSEC, hidioreq_6492a059-8c30-440f-ae98-95d071545408.xml
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
-	IOCTL_HID_SET_POLL_FREQUENCY_MSEC
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_SET_POLL_FREQUENCY_MSEC IOCTL


## -description


The IOCTL_HID_SET_POLL_FREQUENCY_MSEC request sets the polling frequency, in milliseconds, for a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. 

User-mode applications or kernel-mode drivers that perform irregular, opportunistic reads on a polled device must furnish a polling interval of zero. In such cases, IOCTL_HID_SET_POLL_FREQUENCY_MSEC does not actually change the polling frequency of the device; but if the report data is not stale when it is read, the read is completed immediately with the latest report data for the indicated collection. If the report data is stale, it is refreshed immediately, without waiting for the expiration of the polling interval, and the read is completed with the new data. 

If the value for the polling interval that is provided in the IRP is not zero, it must be &gt;= MIN_POLL_INTERVAL_MSEC and &lt;= MAX_POLL_INTERVAL_MSEC.

Polling may be limited if there are multiple top-level collections.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be &gt;= <b>sizeof</b>(ULONG). 

<b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the new polling interval. 


### -input-buffer-length

A value greater than or equal to  <b>sizeof</b>(ULONG).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the <b>Status</b> member of <b>Irp-&gt;IoStatus</b> to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541142">IOCTL_HID_GET_POLL_FREQUENCY_MSEC</a>
 

 

