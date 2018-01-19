---
UID: NF:printoem.OEMAlphaBlend
title: OEMAlphaBlend function
author: windows-driver-content
description: OEMAlphaBlend function
old-location: print\oemalphablend.htm
old-project: print
ms.assetid: c5c7cabe-7ac9-42f7-92e3-2c1c319ce80e
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMAlphaBlend
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
req.alt-api: OEMAlphaBlend
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

# OEMAlphaBlend function



## -description

## -syntax

````
BOOL  APIENTRY OEMAlphaBlend(
   SURFOBJ  *psoDest,
   SURFOBJ  *psoSrc,
   CLIPOBJ  *pco,
   XLATEOBJ *pxlo,
   RECTL    *prclDest,
   RECTL    *prclSrc,
   BLENDOBJ *pBlendObj
);
````


## -parameters

### -param psoDest 


### -param psoSrc 


### -param pco 


### -param pxlo 


### -param prclDest 


### -param prclSrc 


### -param pBlendObj 


## -remarks
