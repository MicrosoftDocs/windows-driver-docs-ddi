---
UID: NI:hidclass.IOCTL_HID_GET_COLLECTION_DESCRIPTOR
title: IOCTL_HID_GET_COLLECTION_DESCRIPTOR (hidclass.h)
description: The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's preparsed data, which the HID class driver extracted from the physical device's report descriptor during device initialization.
old-location: hid\ioctl_hid_get_collection_descriptor.htm
tech.root: hid
ms.assetid: 93684a1a-788d-4b90-b9cc-58a3c4f7b25e
ms.date: 04/30/2018
ms.keywords: IOCTL_HID_GET_COLLECTION_DESCRIPTOR, IOCTL_HID_GET_COLLECTION_DESCRIPTOR control, IOCTL_HID_GET_COLLECTION_DESCRIPTOR control code [Human Input Devices], hid.ioctl_hid_get_collection_descriptor, hidclass/IOCTL_HID_GET_COLLECTION_DESCRIPTOR, hidioreq_3b297887-5287-463a-9a31-46b8bd7761b3.xml
ms.topic: ioctl
f1_keywords:
 - "hidclass/IOCTL_HID_GET_COLLECTION_DESCRIPTOR"
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
- IOCTL_HID_GET_COLLECTION_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_HID_GET_COLLECTION_DESCRIPTOR IOCTL


## -description


The IOCTL_HID_GET_COLLECTION_DESCRIPTOR request obtains a top-level collection's <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>, which the HID class driver extracted from the physical device's report descriptor during device initialization.

For general information about HIDClass devices, see <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/hid-collections">HID Collections</a>. 


## -ioctlparameters




### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer specified by <b>Irp->UserBuffer</b>.


### -input-buffer-length








### -output-buffer

<b>Irp->UserBuffer</b> is a PVOID pointer to a requester-allocated buffer that the HID class driver uses to return a variable length <b>_HIDP_PREPARSED_DATA</b> structure. This buffer must be allocated from nonpaged pool. 


### -output-buffer-length

The size, in bytes, of the preparsed data structure is obtained using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidclass/ni-hidclass-ioctl_hid_get_collection_information">IOCTL_HID_GET_COLLECTION_INFORMATION</a>. 


### -in-out-buffer








### -inout-buffer-length








### -status-block

The HID class driver sets the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to size, in bytes, of the preparesed data.

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the preparsed data was retrieved without error. Otherwise, it is set to an appropriate NTSTATUS error code. If the requester-supplied output buffer is not large enough to hold the preparsed data, then status is set to STATUS_INVALID_BUFFER_SIZE. 

</li>
</ul>

## -remarks



The <b>_HIDP_PREPARSED_DATA</b> structure contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="https://docs.microsoft.com/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _HIDP_PREPARSED_DATA * PHIDP_PREPARSED_DATA;
</pre>
</td>
</tr>
</table></span></div>
A user-mode application calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a> to obtain a top-level collection's preparsed data in a variable length _HIDP_PREPARSED_DATA structure.

A kernel-mode driver uses an <b>IOCTL_HID_GET_COLLECTION_DESCRIPTOR</b> request to obtain a pointer to a top-level collection's preparsed data.

The internal structure of a _HIDP_PREPARSED_DATA structure is reserved for internal system use.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_freepreparseddata">HidD_FreePreparsedData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidsdi/nf-hidsdi-hidd_getpreparseddata">HidD_GetPreparsedData</a>
 

 

