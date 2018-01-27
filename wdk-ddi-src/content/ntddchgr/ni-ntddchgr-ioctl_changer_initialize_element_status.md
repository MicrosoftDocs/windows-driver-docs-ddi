---
UID: NI:ntddchgr.IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
title: IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
author: windows-driver-content
description: Initializes the status of all elements or of specified number of elements of a particular type.
old-location: storage\ioctl_changer_initialize_element_status.htm
old-project: storage
ms.assetid: 25cbb42a-7263-47b7-84c7-cfcb41a858c8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_changer_initialize_element_status, IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS control code [Storage Devices], IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS, ntddchgr/IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS, k307_c36a7809-093c-4172-8443-58d178e9dd87.xml
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
-	IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS
product: Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Initializes the status of all elements or of specified number of elements of a particular type. 




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains an <a href="..\ntddchgr\ns-ntddchgr-_changer_initialize_element_status.md">CHANGER_INITIALIZE_ELEMENT_STATUS</a> structure that indicates the element type and the number of elements to initialize. If the <b>BarCodeScan</b> member is <b>TRUE</b> and CHANGER_BAR_CODE_SCANNER_INSTALLED is also set in <b>Features0</b> of <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>, the elements should be initialized using a bar code scan. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_INITIALIZE_ELEMENT_STATUS). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_ELEMENT_ADDRESS, or STATUS_INVALID_PARAMETER. 


## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_changer_initialize_element_status.md">CHANGER_INITIALIZE_ELEMENT_STATUS</a>

<a href="..\mcd\nf-mcd-changerinitializeelementstatus.md">ChangerInitializeElementStatus</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

