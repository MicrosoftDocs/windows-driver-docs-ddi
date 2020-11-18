---
UID: NF:wdm.KeShouldYieldProcessor
title: KeShouldYieldProcessor
tech.root: kernel
ms.date: 11/8/2019
keywords: ["KeShouldYieldProcessor function"]
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - wdm.h
api_name:
 - KeShouldYieldProcessor
f1_keywords:
 - KeShouldYieldProcessor
 - wdm/KeShouldYieldProcessor
dev_langs:
 - c++
---

# KeShouldYieldProcessor function


## -description

This function advises the caller if it should break out of a work loop running at DISPATCH_LEVEL or higher to allow other processing to take place.

## -returns

Returns TRUE if the caller should lower IRQL to below DISPATCH_LEVEL.

## -remarks

When this function returns TRUE:

* If the caller is running in thread context (i.e. not in an interrupt or DPC), it should lower IRQL to below DISPATCH_LEVEL.
* If the caller is within a DPC or cannot directly lower IRQL, it should queue work to a worker thread and return.

## -see-also

