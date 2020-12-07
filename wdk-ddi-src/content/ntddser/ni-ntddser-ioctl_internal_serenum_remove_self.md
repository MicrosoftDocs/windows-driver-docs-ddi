---
UID: NI:ntddser.IOCTL_INTERNAL_SERENUM_REMOVE_SELF
title: IOCTL_INTERNAL_SERENUM_REMOVE_SELF (ntddser.h)
description: The IOCTL_INTERNAL_SERENUM_REMOVE_SELF request invalidates the bus relations of the filter DO that are associated with a target PDO. (Physically, this request invalidates the bus relations of the RS-232 port to which the target device is attached.).
old-location: serports\ioctl_internal_serenum_remove_self.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["IOCTL_INTERNAL_SERENUM_REMOVE_SELF IOCTL"]
ms.keywords: IOCTL_INTERNAL_SERENUM_REMOVE_SELF, IOCTL_INTERNAL_SERENUM_REMOVE_SELF control, IOCTL_INTERNAL_SERENUM_REMOVE_SELF control code [Serial Ports], ntddser/IOCTL_INTERNAL_SERENUM_REMOVE_SELF, senumref_e7d31955-3eb4-4769-a7fa-84b55272f47a.xml, serports.ioctl_internal_serenum_remove_self
req.header: ntddser.h
req.include-header: Ntddser.h
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
 - IOCTL_INTERNAL_SERENUM_REMOVE_SELF
 - ntddser/IOCTL_INTERNAL_SERENUM_REMOVE_SELF
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddser.h
api_name:
 - IOCTL_INTERNAL_SERENUM_REMOVE_SELF
---

# IOCTL_INTERNAL_SERENUM_REMOVE_SELF IOCTL


## -description

The IOCTL_INTERNAL_SERENUM_REMOVE_SELF request invalidates the bus relations of the filter DO that are associated with a target PDO. (Physically, this request invalidates the bus relations of the RS-232 port to which the target device is attached.)

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

The <b>Status</b> member is set to one of the following values:




**STATUS_DELETE_PENDING**

The device is in the process of being removed.


**STATUS_SUCCESS**

The request completed successfully.

