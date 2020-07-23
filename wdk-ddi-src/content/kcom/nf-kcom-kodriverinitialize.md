---
UID: NF:kcom.KoDriverInitialize
title: KoDriverInitialize function (kcom.h)
description: The KoDriverInitialize function initializes a driver object to handle the kernel streaming interface.
old-location: stream\kodriverinitialize.htm
tech.root: stream
ms.assetid: ed61d135-967d-4e7c-b437-09c9e0e6f3c2
ms.date: 04/23/2018
keywords: ["KoDriverInitialize function"]
ms.keywords: KoDriverInitialize, KoDriverInitialize function [Streaming Media Devices], kcom/KoDriverInitialize, ksfunc_117817ed-5a64-48c4-8b90-1ca6435c75b6.xml, stream.kodriverinitialize
f1_keywords:
 - "kcom/KoDriverInitialize"
 - "KoDriverInitialize"
req.header: kcom.h
req.include-header: Kcom.h
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
- KoDriverInitialize
targetos: Windows
req.typenames: 
---

# KoDriverInitialize function


## -description


<i>This function is intended for internal use only.</i>

The <b>KoDriverInitialize</b> function initializes a driver object to handle the kernel streaming interface. 


## -parameters




### -param DriverObject [in]

Pointer to a driver object to initialize that handles the kernel streaming interface.


### -param RegistryPathName [in]

Pointer to the registry path that is associated with the driver object.


### -param CreateObjectHandler [in]

Pointer to a function used to create new objects.


## -returns



Returns STATUS_SUCCESS if successful. Otherwise, it returns a memory allocation error.



