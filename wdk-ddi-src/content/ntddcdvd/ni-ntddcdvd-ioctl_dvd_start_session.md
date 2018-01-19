---
UID: NI:ntddcdvd.IOCTL_DVD_START_SESSION
title: IOCTL_DVD_START_SESSION
author: windows-driver-content
description: Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.
old-location: storage\ioctl_dvd_start_session.htm
old-project: storage
ms.assetid: a4010756-b230-4e49-85a4-498f5ebcf785
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
req.alt-api: IOCTL_DVD_START_SESSION
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

# IOCTL_DVD_START_SESSION IOCTL



## -description

Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.



Returns an authentication grant ID (AGID) as a DVD session ID, which a caller must pass to the device in all subsequent operations in a DVD session.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The driver returns an integer authentication grant ID of type DVD_SESSION_ID in the buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b>. 


### -output-buffer-length
Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> field is set to <b>sizeof</b>(DVD_SESSION_ID). The <b>Status</b> field is set to STATUS_SUCCESS, or possibly to STATUS_INSUFFICIENT_RESOURCES.


## -remarks
