---
UID: NI:hidclass.IOCTL_HID_GET_HARDWARE_ID
title: IOCTL_HID_GET_HARDWARE_ID
author: windows-driver-content
description: The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a top-level collection.
old-location: hid\ioctl_hid_get_hardware_id.htm
old-project: hid
ms.assetid: 33da3d63-0909-45fe-9a3b-d268b352231c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_HID_GET_HARDWARE_ID, IOCTL_HID_GET_HARDWARE_ID control code [Human Input Devices], hid.ioctl_hid_get_hardware_id, hidclass/IOCTL_HID_GET_HARDWARE_ID, hidioreq_e5eb1673-bf55-451b-b8de-f8d735aa54eb.xml
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
-	IOCTL_HID_GET_HARDWARE_ID
product: Windows
targetos: Windows
req.typenames: HDAUDIO_STREAM_FORMAT, *PHDAUDIO_STREAM_FORMAT
---

# IOCTL_HID_GET_HARDWARE_ID IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


The IOCTL_HID_GET_HARDWARE_ID request obtains the Plug and Play hardware ID of a <a href="https://msdn.microsoft.com/dcbee8e3-d03a-45c8-92e4-0897b9f55177">top-level collection</a>. 

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer. 


### -input-buffer-length

The length of the buffer.


### -output-buffer

<b>Irp-&gt;MdlAddress</b> points to a buffer to receive the number of device input buffers. 


### -output-buffer-length

The length of the buffer.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The HID class driver sets the following fields of <b>Irp-&gt;IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to the number of bytes of registry information retrieved when the IOCTL succeeds. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also

<a href="..\hidclass\ni-hidclass-ioctl_hid_get_indexed_string.md">IOCTL_HID_GET_INDEXED_STRING</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getindexedstring.md">HidD_GetIndexedString</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_manufacturer_string.md">IOCTL_HID_GET_MANUFACTURER_STRING</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_serialnumber_string.md">IOCTL_HID_GET_SERIALNUMBER_STRING</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getmanufacturerstring.md">HidD_GetManufacturerString</a>



<a href="..\hidclass\ni-hidclass-ioctl_hid_get_product_string.md">IOCTL_HID_GET_PRODUCT_STRING</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getproductstring.md">HidD_GetProductString</a>



<a href="..\hidsdi\nf-hidsdi-hidd_getserialnumberstring.md">HidD_GetSerialNumberString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20IOCTL_HID_GET_HARDWARE_ID control code%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

