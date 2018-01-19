---
UID: NF:printoem.OEMFilterGraphics
title: OEMFilterGraphics function
author: windows-driver-content
description: OEMFilterGraphics function
old-location: print\oemfiltergraphics.htm
old-project: print
ms.assetid: 1b81de5a-440a-4209-992e-7f79c047245c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMFilterGraphics
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
req.alt-api: OEMFilterGraphics
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

# OEMFilterGraphics function



## -description

## -syntax

````
BOOL APIENTRY OEMFilterGraphics(
       PDEVOBJ                    pdevobj,
  _In_ _reads_bytes_(dwLen) PBYTE pBuf,
       DWORD                      dwLen
);
````


## -parameters

### -param pdevobj 


### -param pBuf [in]


### -param dwLen 


## -remarks
