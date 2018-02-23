---
UID: NF:ks.KsLoadResource
title: KsLoadResource function
author: windows-driver-content
description: Copies (loads) a resource from the given image.
old-location: stream\ksloadresource.htm
old-project: stream
ms.assetid: a7b9dcca-ce89-4fde-9e58-3c4a675227bc
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ksfunc_d966a58a-b0f0-411f-a19c-1db726efc56e.xml, KsLoadResource, ks/KsLoadResource, stream.ksloadresource, KsLoadResource function [Streaming Media Devices]
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
-	KsLoadResource
product: Windows
targetos: Windows
req.typenames: 
---

# KsLoadResource function


## -description


Copies (loads) a resource from the given image. 


## -syntax


````
NTSTATUS KsLoadResource(
  _In_      PVOID     ImageBase,
  _In_      POOL_TYPE PoolType,
  _In_      ULONG_PTR ResourceName,
  _In_      ULONG     ResourceType,
  _Out_     PVOID     *Resource,
  _Out_opt_ PULONG    ResourceSize
);
````


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



