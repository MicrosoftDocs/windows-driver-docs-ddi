---
UID: NI:ntddstor.IOCTL_STORAGE_RELEASE
title: IOCTL_STORAGE_RELEASE
description: Releases a device previously reserved for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.
old-location: storage\ioctl_storage_release.htm
tech.root: storage
ms.assetid: ca43da4e-6e0e-4689-83db-3f5ee5e560b2
ms.date: 03/29/2018
ms.keywords: IOCTL_STORAGE_RELEASE, IOCTL_STORAGE_RELEASE control, IOCTL_STORAGE_RELEASE control code [Storage Devices], k307_8097610b-98ad-4bb2-9f16-2caca8bf7f0d.xml, ntddstor/IOCTL_STORAGE_RELEASE, storage.ioctl_storage_release
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
-	IOCTL_STORAGE_RELEASE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_STORAGE_RELEASE IOCTL


## -description


Releases a device previously reserved for the exclusive use of the caller on a bus that supports multiple initiators and the concept of reserving a device, such as a SCSI bus.


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

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INVALID_DEVICE_REQUEST.

