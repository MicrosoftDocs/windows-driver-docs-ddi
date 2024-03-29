---
UID: NF:ks.KsValidateAllocatorCreateRequest
title: KsValidateAllocatorCreateRequest function (ks.h)
description: The KsValidateAllocatorCreateRequest function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.
old-location: stream\ksvalidateallocatorcreaterequest.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KsValidateAllocatorCreateRequest function"]
ms.keywords: KsValidateAllocatorCreateRequest, KsValidateAllocatorCreateRequest function [Streaming Media Devices], ks/KsValidateAllocatorCreateRequest, ksfunc_2d988d7a-d39f-4c77-8c18-06d01a8d75e9.xml, stream.ksvalidateallocatorcreaterequest
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
 - KsValidateAllocatorCreateRequest
 - ks/KsValidateAllocatorCreateRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ks.lib
 - Ks.dll
api_name:
 - KsValidateAllocatorCreateRequest
---

# KsValidateAllocatorCreateRequest function


## -description

The <b>KsValidateAllocatorCreateRequest</b> function validates an IRP_MJ_CREATE request as an allocator request and returns the create structure associated with the request on success.

## -parameters

### -param Irp [in]


Specifies the IRP with the IRP_MJ_CREATE request being validated.

### -param AllocatorFraming [out]


Caller-defined pointer that on successful completion contains an address to the framing structure supplied with the request.

## -returns

The <b>KsValidateAllocatorCreateRequest</b> function returns STATUS_SUCCESS if successful, or an error if the allocator request is not valid.

