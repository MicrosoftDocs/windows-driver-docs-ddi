---
UID: NI:ntddchgr.IOCTL_CHANGER_EXCHANGE_MEDIUM
title: IOCTL_CHANGER_EXCHANGE_MEDIUM
author: windows-driver-content
description: Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.
old-location: storage\ioctl_changer_exchange_medium.htm
old-project: storage
ms.assetid: 76f17ee0-5b81-4325-a295-4a6982b49b73
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_CHANGER_EXCHANGE_MEDIUM, IOCTL_CHANGER_EXCHANGE_MEDIUM control code [Storage Devices], k307_c132f9e2-bb9c-43b7-85c2-644f2b24acea.xml, ntddchgr/IOCTL_CHANGER_EXCHANGE_MEDIUM, storage.ioctl_changer_exchange_medium
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddchgr.h
api_name:
-	IOCTL_CHANGER_EXCHANGE_MEDIUM
product:
- Windows
targetos: Windows
req.typenames: ELEMENT_TYPE, *PELEMENT_TYPE
---

# IOCTL_CHANGER_EXCHANGE_MEDIUM IOCTL


## -description



Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.




## -ioctlparameters




### -input-buffer


        The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551464">CHANGER_EXCHANGE_MEDIUM</a> data, which indicates the source, both destinations, and whether either or both media should be flipped, assuming the device supports two-sided media. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be &gt;= <b>sizeof</b>(CHANGER_EXCHANGE_MEDIUM).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DESTINATION_ELEMENT_FULL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_ELEMENT_ADDRESS, STATUS_INVALID_PARAMETER, or STATUS_SOURCE_ELEMENT_EMPTY.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551464">CHANGER_EXCHANGE_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551421">ChangerExchangeMedium</a>
 

 

