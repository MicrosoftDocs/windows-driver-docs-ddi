---
UID: NI:ntddcdvd.IOCTL_AACS_END_SESSION
title: IOCTL_AACS_END_SESSION
author: windows-driver-content
description: Releases the Authentication Grant Identifier (AGID) that was obtained by IOCTL_AACS_START_SESSION.
old-location: storage\ioctl_aacs_end_session.htm
old-project: storage
ms.assetid: 5a86c871-ed6e-4c96-bc12-03b3a900953d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: DVD_STRUCTURE_FORMAT, *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_AACS_END_SESSION
req.alt-loc: Ntddcdvd.h
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
req.typenames: *PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT
---

# IOCTL_AACS_END_SESSION IOCTL



## -description
Releases the Authentication Grant Identifier (AGID) that was obtained by <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_start_session.md">IOCTL_AACS_START_SESSION</a>. 



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session to release. Caller can release all AGIDs for both Advanced Access Content System (AACS) and Content-Scrambling System (CSS) secure sessions by specifying a value DVD_END_ALL_SESSIONS.


### -input-buffer-length
Size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.


### -output-buffer
None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks
