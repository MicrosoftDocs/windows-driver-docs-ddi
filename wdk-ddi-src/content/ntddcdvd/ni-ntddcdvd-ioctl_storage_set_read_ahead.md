---
UID: NI:ntddcdvd.IOCTL_STORAGE_SET_READ_AHEAD
title: IOCTL_STORAGE_SET_READ_AHEAD (ntddcdvd.h)
description: Causes the device to skip to the given target address when the device reaches a certain trigger address during read-ahead caching.
old-location: storage\ioctl_storage_set_read_ahead.htm
tech.root: storage
ms.assetid: a7ed65f3-40a9-4b08-b59d-7c65c250d5cb
ms.date: 03/29/2018
keywords: ["IOCTL_STORAGE_SET_READ_AHEAD IOCTL"]
ms.keywords: IOCTL_STORAGE_SET_READ_AHEAD, IOCTL_STORAGE_SET_READ_AHEAD control, IOCTL_STORAGE_SET_READ_AHEAD control code [Storage Devices], k307_0112afc4-1b4b-47c1-9ace-1d82a41b120f.xml, ntddcdvd/IOCTL_STORAGE_SET_READ_AHEAD, storage.ioctl_storage_set_read_ahead
f1_keywords:
 - "ntddcdvd/IOCTL_STORAGE_SET_READ_AHEAD"
 - "IOCTL_STORAGE_SET_READ_AHEAD"
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
- Ntddcdvd.h
api_name:
- IOCTL_STORAGE_SET_READ_AHEAD
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_SET_READ_AHEAD IOCTL


## -description



Causes the device to skip to the given target address when the device reaches a certain trigger address during read-ahead caching. 




## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_storage_set_read_ahead">STORAGE_SET_READ_AHEAD</a> structure that indicates the trigger and target addresses. 


### -input-buffer-length

The length of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_storage_set_read_ahead">STORAGE_SET_READ_AHEAD</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_storage_set_read_ahead">STORAGE_SET_READ_AHEAD</a>
 

 

