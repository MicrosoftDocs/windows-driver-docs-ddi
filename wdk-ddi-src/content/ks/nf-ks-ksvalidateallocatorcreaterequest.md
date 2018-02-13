---
UID: NF:ks.KsValidateAllocatorCreateRequest
title: KsValidateAllocatorCreateRequest function
author: windows-driver-content
description: The KsValidateAllocatorCreateRequest function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.
old-location: stream\ksvalidateallocatorcreaterequest.htm
old-project: stream
ms.assetid: 9275257b-50d8-4272-b340-4344644b3e15
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ksvalidateallocatorcreaterequest, ks/KsValidateAllocatorCreateRequest, KsValidateAllocatorCreateRequest function [Streaming Media Devices], KsValidateAllocatorCreateRequest, ksfunc_2d988d7a-d39f-4c77-8c18-06d01a8d75e9.xml
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
-	KsValidateAllocatorCreateRequest
product: Windows
targetos: Windows
req.typenames: 
---

# KsValidateAllocatorCreateRequest function


## -description


The <b>KsValidateAllocatorCreateRequest</b> function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.


## -syntax


````
NTSTATUS KsValidateAllocatorCreateRequest(
  _In_  PIRP                 Irp,
  _Out_ PKSALLOCATOR_FRAMING *AllocatorFraming
);
````


## -parameters




### -param Irp [in]

Specifies the IRP with the IRP_MJ_CREATE request being validated.


### -param AllocatorFraming [out]

Caller-defined pointer that on successful completion contains an address to the framing structure supplied with the request.


## -returns



The <b>KsValidateAllocatorCreateRequest</b> function returns STATUS_SUCCESS if successful, or an error if the allocator request is not valid.



