---
UID: NI:ntddcdvd.IOCTL_AACS_END_SESSION
title: IOCTL_AACS_END_SESSION (ntddcdvd.h)
description: Releases the Authentication Grant Identifier (AGID) that was obtained by IOCTL_AACS_START_SESSION.
old-location: storage\ioctl_aacs_end_session.htm
tech.root: storage
ms.assetid: 5a86c871-ed6e-4c96-bc12-03b3a900953d
ms.date: 03/29/2018
keywords: ["IOCTL_AACS_END_SESSION IOCTL"]
ms.keywords: IOCTL_AACS_END_SESSION, IOCTL_AACS_END_SESSION control, IOCTL_AACS_END_SESSION control code [Storage Devices], k307_608ddec6-9661-433b-8b82-22ce3b06267d.xml, ntddcdvd/IOCTL_AACS_END_SESSION, storage.ioctl_aacs_end_session
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
 - IOCTL_AACS_END_SESSION
 - ntddcdvd/IOCTL_AACS_END_SESSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddcdvd.h
api_name:
 - IOCTL_AACS_END_SESSION
---

# IOCTL_AACS_END_SESSION IOCTL


## -description

Releases the Authentication Grant Identifier (AGID) that was obtained by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_start_session">IOCTL_AACS_START_SESSION</a>.

## -ioctlparameters

### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session to release. Caller can release all AGIDs for both Advanced Access Content System (AACS) and Content-Scrambling System (CSS) secure sessions by specifying a value DVD_END_ALL_SESSIONS.

### -input-buffer-length

Size of a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff553743(v=vs.85)">DVD_SESSION_ID</a>.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.

