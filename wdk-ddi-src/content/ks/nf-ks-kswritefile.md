---
UID: NF:ks.KsWriteFile
title: KsWriteFile function (ks.h)
description: The KsWriteFile function performs a write against the specified file object.
old-location: stream\kswritefile.htm
tech.root: stream
ms.assetid: ed66db40-d159-4660-96c0-da52f752a409
ms.date: 04/23/2018
keywords: ["KsWriteFile function"]
ms.keywords: KsWriteFile, KsWriteFile function [Streaming Media Devices], ks/KsWriteFile, ksfunc_4e15871e-8093-4b8e-a1ec-0eda4588e262.xml, stream.kswritefile
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
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
req.lib: Ks.lib
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - KsWriteFile
 - ks/KsWriteFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsWriteFile
---

# KsWriteFile function


## -description

The <b>KsWriteFile</b> function performs a write against the specified file object. It is assumed that the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object. The function attempts to use <b>FastIoDispatch</b> if possible, or it generates a write request against the device object. All relevant statistics are updated.

## -parameters

### -param FileObject 

[in]
Specifies the file object to perform the read against.

### -param Event 

[in, optional]
Optionally contains the event to use in the write. If no event is passed, the call is assumed to be on a synchronous file object or the caller is waiting for the file object's event. If the call is not on a synchronous file object, it can be asynchronously completed. If the file has been opened for synchronous I/O, this variable must be <b>NULL</b>. If this variable is used, it must be an event allocated by the object manager.

### -param PortContext 

[in, optional]
Optionally contains context information for a completion port.

### -param IoStatusBlock 

[out]
Indicates the location in which to return the status information. This is always assumed to be a valid address, regardless of the requester mode.

### -param Buffer 

[in]
Specifies the buffer from which to write the data. If the buffer needs to be probed and locked, an exception handler is used, along with <i>RequesterMode</i>.

### -param Length 

[in]
Specifies the size of the buffer passed.

### -param OPTIONAL

### -param RequestorMode 

[in]
Indicates the processor mode to place in the read IRP if one needs to be generated. Additionally, it is used if a buffer needs to be probed and locked. This variable also determines if a fast I/O call can be performed. If the requester mode is not KernelMode, but the previous mode was, then fast I/O cannot be used.


#### - Key [in, optional]

Optionally contains a key, or zero if none.

## -returns

The <b>KsWriteFile</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or it returns a read error if unsuccessful.

