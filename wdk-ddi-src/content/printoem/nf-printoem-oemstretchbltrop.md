---
UID: NF:printoem.OEMStretchBltROP
title: OEMStretchBltROP function
author: windows-driver-content
description: The OEMStretchBltROP function performs a stretching bit-block transfer using a raster operation (ROP).
old-location: print\oemstretchbltrop.htm
old-project: print
ms.assetid: 2e265dc6-3e04-4f25-ae3b-6cb7ce5ce9ae
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print_unidrv-pscript_rendering_b1617a87-83e0-4b49-b123-e1db1ed3dd70.xml, print.oemstretchbltrop, OEMStretchBltROP, printoem/OEMStretchBltROP, OEMStretchBltROP function [Print Devices]
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
-	OEMStretchBltROP
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStretchBltROP function


## -description


The <code>OEMStretchBltROP</code> function performs a stretching bit-block transfer using a <a href="https://msdn.microsoft.com/004698f5-cb0e-4995-a19c-7075aa226000">raster operation (ROP)</a>.


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

