---
UID: NI:ntddchgr.IOCTL_CHANGER_MOVE_MEDIUM
title: IOCTL_CHANGER_MOVE_MEDIUM
author: windows-driver-content
description: Moves a piece of media from a source element to a destination.
old-location: storage\ioctl_changer_move_medium.htm
old-project: storage
ms.assetid: 4a410f56-cdc1-4cb0-801c-62402caec4ee
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.ioctl_changer_move_medium, IOCTL_CHANGER_MOVE_MEDIUM control code [Storage Devices], IOCTL_CHANGER_MOVE_MEDIUM, ntddchgr/IOCTL_CHANGER_MOVE_MEDIUM, k307_4d55c834-2f72-433b-8e75-015908324d87.xml
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
-	IOCTL_CHANGER_MOVE_MEDIUM
product: Windows
targetos: Windows
req.typenames: "*PELEMENT_TYPE, ELEMENT_TYPE"
---

# IOCTL_CHANGER_MOVE_MEDIUM IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Moves a piece of media from a source element to a destination.




## -ioctlparameters




### -input-buffer


       The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="..\ntddchgr\ns-ntddchgr-_changer_move_medium.md">CHANGER_MOVE_MEDIUM</a> data, which indicates the transport to use for the operation, the source, the destination, and whether the medium should be flipped, assuming the device supports two-sided media. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_MOVE_MEDIUM). 


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to <b>sizeof</b>(CHANGER_MOVE_MEDIUM). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DESTINATION_ELEMENT_FULL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_ELEMENT_ADDRESS, STATUS_INVALID_PARAMETER, or STATUS_SOURCE_ELEMENT_EMPTY. 


## -see-also

<a href="..\mcd\nf-mcd-changermovemedium.md">ChangerMoveMedium</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_move_medium.md">CHANGER_MOVE_MEDIUM</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IOCTL_CHANGER_MOVE_MEDIUM control code%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

