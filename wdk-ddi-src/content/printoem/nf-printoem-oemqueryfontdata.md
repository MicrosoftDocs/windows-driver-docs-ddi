---
UID: NF:printoem.OEMQueryFontData
title: OEMQueryFontData function
author: windows-driver-content
description: The OEMQueryFontData function retrieves information about a realized font.
old-location: print\oemqueryfontdata.htm
old-project: print
ms.assetid: dccf1bca-6ea5-4cf0-b768-b569898c90e7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMQueryFontData
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
req.alt-api: OEMQueryFontData
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

# OEMQueryFontData function



## -description
The <code>OEMQueryFontData</code> function retrieves information about a realized font. 



## -syntax

````
LONG APIENTRY OEMQueryFontData(
        DHPDEV                       dhpdev,
        FONTOBJ                      *pfo,
        ULONG                        iMode,
        HGLYPH                       hg,
        GLYPHDATA                    *pgd,
  _Out_ _writes_bytes_(cjSize) PVOID pv,
        ULONG                        cjSize
);
````


## -parameters

### -param dhpdev 


### -param pfo 


### -param iMode 


### -param hg 


### -param pgd 


### -param pv [out]


### -param cjSize 


## -remarks
