---
UID: NF:printoem.OEMStretchBltROP
title: OEMStretchBltROP function
author: windows-driver-content
description: The OEMStretchBltROP function performs a stretching bit-block transfer using a raster operation (ROP).
old-location: print\oemstretchbltrop.htm
old-project: print
ms.assetid: 2e265dc6-3e04-4f25-ae3b-6cb7ce5ce9ae
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMStretchBltROP
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
req.alt-api: OEMStretchBltROP
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

# OEMStretchBltROP function



## -description
The <code>OEMStretchBltROP</code> function performs a stretching bit-block transfer using a <a href="wdkgloss.r#wdkgloss.raster_operation__rop_#wdkgloss.raster_operation__rop_"><i>raster operation (ROP)</i></a>.



## -syntax

````
BOOL APIENTRY OEMStretchBltROP(
   SURFOBJ         *psoDest,
   SURFOBJ         *psoSrc,
   SURFOBJ         *psoMask,
   CLIPOBJ         *pco,
   XLATEOBJ        *pxlo,
   COLORADJUSTMENT *pca,
   POINTL          *pptlHTOrg,
   RECTL           *prclDest,
   RECTL           *prclSrc,
   POINTL          *pptlMask,
   ULONG           iMode,
   BRUSHOBJ        *pbo,
   ROP4            rop4
);
````


## -parameters

### -param psoDest 


### -param psoSrc 


### -param psoMask 


### -param pco 


### -param pxlo 


### -param pca 


### -param pptlHTOrg 


### -param prclDest 


### -param prclSrc 


### -param pptlMask 


### -param iMode 


### -param pbo 


### -param rop4 


## -remarks
