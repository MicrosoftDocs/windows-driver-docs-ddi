---
UID: NF:ks.KsLoadResource
title: KsLoadResource function (ks.h)
description: Copies (loads) a resource from the given image.
old-location: stream\ksloadresource.htm
tech.root: stream
ms.assetid: a7b9dcca-ce89-4fde-9e58-3c4a675227bc
ms.date: 04/23/2018
keywords: ["KsLoadResource function"]
ms.keywords: KsLoadResource, KsLoadResource function [Streaming Media Devices], ks/KsLoadResource, ksfunc_d966a58a-b0f0-411f-a19c-1db726efc56e.xml, stream.ksloadresource
f1_keywords:
 - "ks/KsLoadResource"
 - "KsLoadResource"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Ks.lib
- Ks.dll
api_name:
- KsLoadResource
targetos: Windows
req.typenames: 
---

# KsLoadResource function


## -description


Copies (loads) a resource from the given image. 


## -parameters




### -param ImageBase [in]

Pointer to the image base


### -param PoolType [in]

Pool type to use when copying resource


### -param ResourceName [in]

Resource name.


### -param ResourceType [in]

Resource type


### -param Resource [out]

Pointer to resultant resource memory.


### -param ResourceSize [out, optional]

Pointer to ULONG value to receive the size of the resource.


## -returns



STATUS_SUCCESS if successful, STATUS_INSUFFICIENT_RESOURCES if memory cannot be allocated, otherwise an appropriate error code.



