---
UID: NI:ntddcdvd.IOCTL_DVD_END_SESSION
title: IOCTL_DVD_END_SESSION (ntddcdvd.h)
description: Ends a DVD session by invalidating its authentication grant ID (AGID).
old-location: storage\ioctl_dvd_end_session.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["IOCTL_DVD_END_SESSION IOCTL"]
ms.keywords: IOCTL_DVD_END_SESSION, IOCTL_DVD_END_SESSION control, IOCTL_DVD_END_SESSION control code [Storage Devices], k307_6d285513-0b3e-4493-977e-e6e837fa3d6a.xml, ntddcdvd/IOCTL_DVD_END_SESSION, storage.ioctl_dvd_end_session
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_DVD_END_SESSION
 - ntddcdvd/IOCTL_DVD_END_SESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_DVD_END_SESSION
---

# IOCTL_DVD_END_SESSION IOCTL


## -description

Ends a DVD session by invalidating its authentication grant ID (AGID).

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains the session ID.

### -input-buffer-length

Length of a session ID.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS.

