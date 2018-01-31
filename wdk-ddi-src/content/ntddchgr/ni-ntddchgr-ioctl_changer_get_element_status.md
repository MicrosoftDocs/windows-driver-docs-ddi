---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_ELEMENT_STATUS
title: IOCTL_CHANGER_GET_ELEMENT_STATUS
author: windows-driver-content
description: Returns the status of all elements or the status of a specified number of elements of a particular type. For a description of the possible element types, see CHANGER_ELEMENT.
old-location: storage\ioctl_changer_get_element_status.htm
old-project: storage
ms.assetid: 5611bd28-16ed-4af1-a01c-07ef590bad65
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_changer_get_element_status, IOCTL_CHANGER_GET_ELEMENT_STATUS control code [Storage Devices], IOCTL_CHANGER_GET_ELEMENT_STATUS, ntddchgr/IOCTL_CHANGER_GET_ELEMENT_STATUS, k307_017d1ca9-974c-4a25-b28f-51e0bdc562d8.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddchgr.h
req.include-header: Ntddchgr.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddchgr.h
apiname:
-	IOCTL_CHANGER_GET_ELEMENT_STATUS
product: Windows
targetos: Windows
req.typenames: "*PELEMENT_TYPE, ELEMENT_TYPE"
---

# IOCTL_CHANGER_GET_ELEMENT_STATUS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Returns the status of all elements or the status of a specified number of elements of a particular type. 

For a description of the possible element types, see <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>.




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntddchgr\ns-ntddchgr-_changer_read_element_status.md">CHANGER_READ_ELEMENT_STATUS</a> data that indicates the element type and the number of elements for which to return status.

If the caller sets the <b>VolumeTagInfo</b> member of CHANGER_READ_ELEMENT_STATUS to <b>TRUE</b>, the element status that is returned will include volume tag information. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer for input, which must be &gt;= <b>sizeof</b>(CHANGER_READ_ELEMENT_STATUS). 


### -output-buffer

The changer miniclass driver returns the changer element status data in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. Some elements of type <b>ChangerDrive</b> return product information data. If the device provides product information, the miniclass driver will report the element status data in a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status_ex.md">CHANGER_ELEMENT_STATUS_EX</a>. The miniclass driver sets ELEMENT_STATUS_PRODUCT_DATA in the <b>Flags</b> member of the structure to indicate that it contains product information data. For elements of all types other than <b>ChangerDrive</b>, the driver reports element status data in a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>. 


### -output-buffer-length

<b>Parameters.DeviceIoControl.OutputBufferLength</b> indicates the size, in bytes, of the parameter buffer for output. For elements of type <b>ChangerDrive</b>, this value must be &gt;= <i>NumberOfElements</i> * <b>sizeof</b>(CHANGER_ELEMENT_STATUS_EX). For elements of all other types, this value must be &gt;= <i>NumberOfElements</i> * <b>sizeof</b>(CHANGER_ELEMENT_STATUS). 


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes returned. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_BUFFER_TOO_SMALL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. 


## -see-also

<a href="..\mcd\nf-mcd-changergetelementstatus.md">ChangerGetElementStatus</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status_ex.md">CHANGER_ELEMENT_STATUS_EX</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_GET_ELEMENT_STATUS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

