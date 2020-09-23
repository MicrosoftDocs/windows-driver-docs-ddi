---
UID: NI:hidclass.IOCTL_HID_GET_COLLECTION_INFORMATION
title: IOCTL_HID_GET_COLLECTION_INFORMATION (hidclass.h)
description: The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a top-level collection's HID_COLLECTION_INFORMATION structure.
old-location: hid\ioctl_hid_get_collection_information.htm
tech.root: hid
ms.assetid: 4d080a3d-7277-4bc5-b435-af2c334862ca
ms.date: 04/30/2018
keywords: ["IOCTL_HID_GET_COLLECTION_INFORMATION IOCTL"]
ms.keywords: IOCTL_HID_GET_COLLECTION_INFORMATION, IOCTL_HID_GET_COLLECTION_INFORMATION control, IOCTL_HID_GET_COLLECTION_INFORMATION control code [Human Input Devices], hid.ioctl_hid_get_collection_information, hidclass/IOCTL_HID_GET_COLLECTION_INFORMATION, hidioreq_f9030552-353d-4f1d-ae66-9689e8c9ad12.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_HID_GET_COLLECTION_INFORMATION
 - hidclass/IOCTL_HID_GET_COLLECTION_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hidclass.h
api_name:
 - IOCTL_HID_GET_COLLECTION_INFORMATION
---

# IOCTL_HID_GET_COLLECTION_INFORMATION IOCTL


## -description

The IOCTL_HID_GET_COLLECTION_INFORMATION request obtains a <a href="/windows-hardware/drivers/hid/top-level-collections">top-level collection's</a> <a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_collection_information">HID_COLLECTION_INFORMATION</a> structure. This information includes the size, in bytes, of a collection's <a href="/windows-hardware/drivers/hid/preparsed-data">preparsed data</a>.

For general information about HIDClass devices, see <a href="/windows-hardware/drivers/hid/hid-collections">HID Collections</a>.

## -ioctlparameters

### -input-buffer

<b>Parameters.DeviceIoControl.OutputBufferLength</b> in the I/O stack location of the IRP indicates the size, in bytes, of the output buffer, which must be >= <b>sizeof</b>(HID_COLLECTION_INFORMATION).

### -input-buffer-length

Greater than or equal to <b>sizeof</b>(HID_COLLECTION_INFORMATION).

### -output-buffer

<b>Irp->AssociatedIrp.SystemBuffer</b> points to a buffer that will receive the collection information. This data will be formatted in the requester-supplied buffer as a HID_COLLECTION_INFORMATION structure.

### -output-buffer-length

The size of a HID_COLLECTION_INFORMATION structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The HID class driver sets the following fields of <b>Irp->IoStatus</b>:

<ul>
<li>
<b>Information</b> is set to <b>sizeof</b>(HID_COLLECTION_INFORMATION) if the data was retrieved successfully. 

</li>
<li>
<b>Status</b> is set to STATUS_SUCCESS if the transfer completed without error. Otherwise, it is set to an appropriate NTSTATUS error code.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/hidclass/ns-hidclass-_hid_collection_information">HID_COLLECTION_INFORMATION</a>