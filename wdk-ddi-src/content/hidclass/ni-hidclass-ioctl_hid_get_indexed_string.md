---
UID: NI:hidclass.IOCTL_HID_GET_INDEXED_STRING
title: IOCTL_HID_GET_INDEXED_STRING
author: windows-driver-content
description: The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a top-level collection.
old-location: hid\ioctl_hid_get_indexed_string2.htm
old-project: hid
ms.assetid: e97ce2a6-a852-4631-901f-b4cfd3834e04
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: IOCTL_HID_GET_INDEXED_STRING, IOCTL_HID_GET_INDEXED_STRING control, IOCTL_HID_GET_INDEXED_STRING control code [Human Input Devices], hid.ioctl_hid_get_indexed_string2, hidclass/IOCTL_HID_GET_INDEXED_STRING, hidioreq_ab829578-5003-4082-9c70-d81d59fb5015.xml
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
-	IOCTL_HID_GET_INDEXED_STRING
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_INDEXED_STRING IOCTL


## -description


The IOCTL_HID_GET_INDEXED_STRING request obtains a specified embedded string from a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. The retrieved string is a NULL-terminated wide character string in a human-readable format.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location of the IRP indicates the size in bytes of the input buffer at the location pointed to by <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer.  

<b>Minidriver handling</b>

IOCTL_HID_GET_INDEXED_STRING uses two input buffers.

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer at the location pointed to by <b>Irp-&gt;MdlAddress</b>. If the output buffer is not large enough to hold the entire NULL-terminated embedded string, the request returns nothing in the output buffer. The maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).

<b>Parameters.DeviceIoControl.Type3InputBuffer</b> contains an INT value that describes the string to be retrieved. The most significant two bytes of the INT value contain the language ID (for example, a value of 1033 indicates English). The least significant two bytes of the INT value contain the string index.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> must be &gt;= <b>sizeof</b>(ULONG) and it should contain the index of the string to be retrieved. 

For <b>Parameters.DeviceIoControl.OutputBufferLength</b>, the maximum possible number of characters in an embedded string is device specific. For USB devices, the maximum string length is 126 wide characters (not including the terminating NULL character).


### -output-buffer

<b>Irp-&gt;MdlAddress</b> points to a buffer to receive the retrieved string (a NULL-terminated wide character string).

<b>Minidriver handling</b>

<b>Irp-&gt;MdlAddress</b> points to a buffer to receive the retrieved string (a NULL-terminated wide character string). Note that unlike most device control IRPs for HID minidrivers, this IRP does not use METHOD_NEITHER buffering. In particular, it must be distinguished from IOCTL_HID_GET_STRING whose output buffer is identified by <b>Irp-&gt;UserBuffer</b>.


### -output-buffer-length

The length of the retrieved string  (a NULL-terminated wide character string).


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes transferred from the device.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538927">HidD_GetIndexedString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538959">HidD_GetManufacturerString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539677">HidD_GetPhysicalDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539681">HidD_GetProductString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539683">HidD_GetSerialNumberString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541134">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541146">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541160">IOCTL_HID_GET_SERIALNUMBER_STRING</a>
 

 

