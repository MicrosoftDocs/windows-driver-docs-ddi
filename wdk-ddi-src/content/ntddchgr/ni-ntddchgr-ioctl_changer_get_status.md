---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_STATUS
title: IOCTL_CHANGER_GET_STATUS
description: Returns the current status of the device.
old-location: storage\ioctl_changer_get_status.htm
tech.root: storage
ms.assetid: 88f1a248-0beb-4c7c-b68d-6ce145bf5ca7
ms.date: 03/29/2018
ms.keywords: IOCTL_CHANGER_GET_STATUS, IOCTL_CHANGER_GET_STATUS control, IOCTL_CHANGER_GET_STATUS control code [Storage Devices], k307_81e37b47-2d26-466d-9ddc-cc681398d607.xml, ntddchgr/IOCTL_CHANGER_GET_STATUS, storage.ioctl_changer_get_status
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
-	IOCTL_CHANGER_GET_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_CHANGER_GET_STATUS IOCTL


## -description


Returns the current status of the device.


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

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES. 

