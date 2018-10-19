---
UID: NI:ntddstor.IOCTL_STORAGE_RESERVE
title: IOCTL_STORAGE_RESERVE
author: windows-driver-content
description: Claims a device for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.
old-location: storage\ioctl_storage_reserve.htm
tech.root: storage
ms.assetid: acafac18-63c7-4965-a1d6-e7c961507b4b
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_RESERVE, IOCTL_STORAGE_RESERVE control, IOCTL_STORAGE_RESERVE control code [Storage Devices], k307_3cb0baa4-c551-44a1-8728-c0053ab04e79.xml, ntddstor/IOCTL_STORAGE_RESERVE, storage.ioctl_storage_reserve
ms.topic: ioctl
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	Ntddstor.h
api_name:
-	IOCTL_STORAGE_RESERVE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_RESERVE IOCTL


## -description



Claims a device for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST, STATUS_DEVICE_NOT_CONNECTED, or STATUS_IO_TIMEOUT.

