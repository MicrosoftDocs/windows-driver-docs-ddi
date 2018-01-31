---
UID: NI:ntddchgr.IOCTL_CHANGER_SET_ACCESS
title: IOCTL_CHANGER_SET_ACCESS
author: windows-driver-content
description: Sets the state of the device's import/export port (IEport), door, or keypad.
old-location: storage\ioctl_changer_set_access.htm
old-project: storage
ms.assetid: 8927e862-94e4-45ce-9245-5c6f5629fc01
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_changer_set_access, IOCTL_CHANGER_SET_ACCESS control code [Storage Devices], IOCTL_CHANGER_SET_ACCESS, ntddchgr/IOCTL_CHANGER_SET_ACCESS, k307_08d52a8e-d7a0-42c6-92f9-c5099670473c.xml
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
-	IOCTL_CHANGER_SET_ACCESS
product: Windows
targetos: Windows
req.typenames: "*PELEMENT_TYPE, ELEMENT_TYPE"
---

# IOCTL_CHANGER_SET_ACCESS IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Sets the state of the device's import/export port (IEport), door, or keypad. 




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a <a href="..\ntddchgr\ns-ntddchgr-_changer_set_access.md">CHANGER_SET_ACCESS</a> structure indicating the element and the operation to perform.


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_SET_ACCESS). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes set. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, or STATUS_INVALID_PARAMETER. 


## -see-also

<a href="..\mcd\nf-mcd-changersetaccess.md">ChangerSetAccess</a>

<a href="..\ntddchgr\ns-ntddchgr-_changer_set_access.md">CHANGER_SET_ACCESS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_SET_ACCESS control code%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

