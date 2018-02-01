---
UID: NF:printoem.OEMStretchBlt
title: OEMStretchBlt function
author: windows-driver-content
description: The OEMStretchBlt function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces.
old-location: print\oemstretchblt.htm
old-project: print
ms.assetid: 5a533a68-6bdb-45dc-b5d3-04fa8d3e7129
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: OEMStretchBlt, print.oemstretchblt, OEMStretchBlt function [Print Devices], print_unidrv-pscript_rendering_cbbd51bd-2201-4fd4-9b3e-1e86f3962be8.xml, printoem/OEMStretchBlt
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMStretchBlt
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStretchBlt function


## -description


The <code>OEMStretchBlt</code> function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces. 


## -syntax


````
BOOL APIENTRY OEMStretchBlt(
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
   ULONG           iMode
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


