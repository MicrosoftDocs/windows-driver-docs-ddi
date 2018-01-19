---
UID: NI:ntddcdvd.IOCTL_DVD_END_SESSION
title: IOCTL_DVD_END_SESSION
author: windows-driver-content
description: Ends a DVD session by invalidating its authentication grant ID (AGID).
old-location: storage\ioctl_dvd_end_session.htm
old-project: storage
ms.assetid: 70908275-211b-4112-bad3-35584ec1ef10
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
req.alt-api: IOCTL_DVD_END_SESSION
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

# IOCTL_DVD_END_SESSION IOCTL



## -description

Ends a DVD session by invalidating its authentication grant ID (AGID).



Ends a DVD session by invalidating its authentication grant ID (AGID).



## -ioctlparameters

### -input-buffer
The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the session ID. 


### -input-buffer-length
Length of a session ID.


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
The <b>Information</b> field is set to zero. The <b>Status</b> field is set to STATUS_SUCCESS.


## -remarks
