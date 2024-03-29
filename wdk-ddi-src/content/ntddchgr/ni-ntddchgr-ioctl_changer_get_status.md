---
UID: NI:ntddchgr.IOCTL_CHANGER_GET_STATUS
title: IOCTL_CHANGER_GET_STATUS (ntddchgr.h)
description: Returns the current status of the device.
old-location: storage\ioctl_changer_get_status.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_CHANGER_GET_STATUS IOCTL"]
ms.keywords: IOCTL_CHANGER_GET_STATUS, IOCTL_CHANGER_GET_STATUS control, IOCTL_CHANGER_GET_STATUS control code [Storage Devices], k307_81e37b47-2d26-466d-9ddc-cc681398d607.xml, ntddchgr/IOCTL_CHANGER_GET_STATUS, storage.ioctl_changer_get_status
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_CHANGER_GET_STATUS
 - ntddchgr/IOCTL_CHANGER_GET_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddchgr.h
api_name:
 - IOCTL_CHANGER_GET_STATUS
---

# IOCTL_CHANGER_GET_STATUS IOCTL


## -description

Returns the current status of the device.

## -ioctlparameters

### -ioctl-major-code

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

