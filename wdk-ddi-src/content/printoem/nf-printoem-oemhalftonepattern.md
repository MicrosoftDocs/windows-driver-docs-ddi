---
UID: NF:printoem.OEMHalftonePattern
title: OEMHalftonePattern function
author: windows-driver-content
description: OEMHalftonePattern function
old-location: print\oemhalftonepattern.htm
old-project: print
ms.assetid: c574d997-736e-4883-a2c3-447985fcee55
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMHalftonePattern
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OEMHalftonePattern
req.alt-loc: printoem.h
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMHalftonePattern function



## -description

## -syntax

````
BOOL APIENTRY OEMHalftonePattern(
       PDEVOBJ                                 pdevobj,
       PBYTE                                   pHTPattern,
       DWORD                                   dwHTPatternX,
       DWORD                                   dwHTPatternY,
       DWORD                                   dwHTNumPatterns,
       DWORD                                   dwCallbackID,
  _In_ _reads_bytes_opt_(dwResourceSize) PBYTE pResource,
       DWORD                                   dwResourceSize
);
````


## -parameters

### -param pdevobj 


### -param pHTPattern 


### -param dwHTPatternX 


### -param dwHTPatternY 


### -param dwHTNumPatterns 


### -param dwCallbackID 


### -param pResource [in]


### -param dwResourceSize 


## -remarks
