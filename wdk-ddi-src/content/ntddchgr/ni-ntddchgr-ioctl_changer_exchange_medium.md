---
UID: NI:ntddchgr.IOCTL_CHANGER_EXCHANGE_MEDIUM
title: IOCTL_CHANGER_EXCHANGE_MEDIUM (ntddchgr.h)
description: Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.
old-location: storage\ioctl_changer_exchange_medium.htm
tech.root: storage
ms.assetid: 76f17ee0-5b81-4325-a295-4a6982b49b73
ms.date: 03/29/2018
keywords: ["IOCTL_CHANGER_EXCHANGE_MEDIUM IOCTL"]
ms.keywords: IOCTL_CHANGER_EXCHANGE_MEDIUM, IOCTL_CHANGER_EXCHANGE_MEDIUM control, IOCTL_CHANGER_EXCHANGE_MEDIUM control code [Storage Devices], k307_c132f9e2-bb9c-43b7-85c2-644f2b24acea.xml, ntddchgr/IOCTL_CHANGER_EXCHANGE_MEDIUM, storage.ioctl_changer_exchange_medium
f1_keywords:
 - "ntddchgr/IOCTL_CHANGER_EXCHANGE_MEDIUM"
 - "IOCTL_CHANGER_EXCHANGE_MEDIUM"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddchgr.h
api_name:
- IOCTL_CHANGER_EXCHANGE_MEDIUM
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_EXCHANGE_MEDIUM IOCTL


## -description



Moves a piece of media from a source element to one destination and the piece of media originally in the first destination to a second destination. The source and second destination are often the same, which essentially swaps the two pieces of media.




## -ioctlparameters




### -input-buffer


        The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_exchange_medium">CHANGER_EXCHANGE_MEDIUM</a> data, which indicates the source, both destinations, and whether either or both media should be flipped, assuming the device supports two-sided media. 


### -input-buffer-length

<b>Parameters.DeviceIoControl.InputBufferLength</b> in the I/O stack location indicates the size, in bytes, of the parameter buffer, which must be >= <b>sizeof</b>(CHANGER_EXCHANGE_MEDIUM).


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_DESTINATION_ELEMENT_FULL, STATUS_INFO_LENGTH_MISMATCH, STATUS_INSUFFICIENT_RESOURCES, STATUS_INVALID_DEVICE_REQUEST, STATUS_INVALID_ELEMENT_ADDRESS, STATUS_INVALID_PARAMETER, or STATUS_SOURCE_ELEMENT_EMPTY.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_exchange_medium">CHANGER_EXCHANGE_MEDIUM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerexchangemedium">ChangerExchangeMedium</a>
 

 

