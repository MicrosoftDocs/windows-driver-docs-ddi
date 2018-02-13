---
UID: NF:ks.KsReadFile
title: KsReadFile function
author: windows-driver-content
description: The KsReadFile function performs a read against the specified file object.
old-location: stream\ksreadfile.htm
old-project: stream
ms.assetid: e3bb6ead-8129-4605-8755-3a56d4b3d8f6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksreadfile, ks/KsReadFile, KsReadFile, ksfunc_9264bdad-2acc-46fe-9ca3-d006bf6c3e23.xml, KsReadFile function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Ks.lib
-	Ks.dll
apiname:
-	KsReadFile
product: Windows
targetos: Windows
req.typenames: 
---

# KsReadFile function


## -description


The <b>KsReadFile</b> function performs a read against the specified file object. It is assumed the caller is serializing access to the file for operations against a FO_SYNCHRONOUS_IO file object. The function attempts to use <b>FastIoDispatch</b> if possible, or generates a read request against the device object. All relevant statistics are updated.


## -syntax


````
NTSTATUS KsReadFile(
  _In_     PFILE_OBJECT     FileObject,
  _In_opt_ PKEVENT          Event,
  _In_opt_ PVOID            PortContext,
  _Out_    PIO_STATUS_BLOCK IoStatusBlock,
  _Out_    PVOID            Buffer,
  _In_     ULONG            Length,
  _In_opt_ ULONG            Key,
  _In_     KPROCESSOR_MODE  RequestorMode
);
````


## -parameters




### -param FileObject [in]

Specifies the file object to perform the read against.


### -param Event [in, optional]

Optionally contains the event to use in the read. If no event is passed, the call is assumed to be on a synchronous file object. If not, the caller is waiting for the file object's event, or it may be asynchronously completed. If the file has been opened for synchronous I/O, this must be <b>NULL</b>. If the variable is used, it must be an event allocated by the object manager.


### -param PortContext [in, optional]

Optionally contains context information for a completion port.


### -param IoStatusBlock [out]

Specifies the address where the status information is to be returned. This is always assumed to be a valid address, regardless of the requester mode.


### -param Buffer [out]

Specifies the buffer in which to place the data read. If the buffer needs to be probed and locked, an exception handler is used, along with <i>RequesterMode</i>.


### -param Length [in]

Specifies the size of the buffer passed.


### -param OPTIONAL

TBD


### -param RequestorMode [in]

Indicates the processor mode to place in the read IRP if one needs to be generated. Additionally, it is used if the buffer needs to be probed and locked. This variable also determines if a fast I/O call can be performed. If the requester mode is not KernelMode, but the previous mode was, then fast I/O cannot be used.


#### - Key [in, optional]

Optionally contains a key, or zero if none


## -returns



The <b>KsReadFile</b> function returns STATUS_SUCCESS if successful, STATUS_PENDING if action is pending, or it returns a read error if unsuccessful.



