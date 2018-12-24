---
UID: NF:ks.KsAllocateExtraData
title: KsAllocateExtraData function
description: The KsAllocateExtraData function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller.
old-location: stream\ksallocateextradata.htm
tech.root: stream
ms.assetid: dfeaca74-d34d-4128-bd76-3a1bf1b3f5d6
ms.date: 04/23/2018
ms.keywords: KsAllocateExtraData, KsAllocateExtraData function [Streaming Media Devices], ks/KsAllocateExtraData, ksfunc_a6f4b047-cec7-4c0d-850f-c3d3b1d1e33e.xml, stream.ksallocateextradata
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
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ks.lib
-	Ks.dll
api_name:
-	KsAllocateExtraData
product:
- Windows
targetos: Windows
req.typenames: 
---

# KsAllocateExtraData function


## -description


The <b>KsAllocateExtraData</b> function is used with streaming IRPs to allocate a buffer to contain additional header data. A pointer to the allocated buffer is returned, and the buffer must eventually be freed by the caller. 


## -parameters




### -param Irp [in, out]

Specifies the IRP containing the stream headers. The IRP must have been previously passed to <b>KsProbeStreamIrp</b> to buffer the headers.


### -param ExtraSize [in]

Specifies the size, in bytes, of additional memory to allocate between each stream header. This value <i>must</i> be alignable on an eight-byte boundary. A copy of the headers is placed in the returned buffer, with the extra data size inserted between each header. This must be freed by the caller.


### -param ExtraBuffer [out]

Points to a caller-allocated pointer that, on successful completion, points to a system-allocated buffer containing the stream headers and the requested padding between them. This must be freed by the caller.


## -returns



The <b>KsAllocateExtraData</b> function returns STATUS_SUCCESS if successful, or it returns a resource or access error.




## -remarks



When <b>KsAllocateExtraData</b> completes successfully, a pointer to a block of memory is returned that contains both the stream data headers from the IRP, specified at <i>Irp</i>, and padding between each header of size specified in <i>ExtraSize</i>. An example of such a resultant buffer is shown below:

![Diagram illustrating a resultant buffer](images/ksexdata.png)

When the extra buffer is no longer needed, the memory should be freed using <b>ExFreePool</b>.



