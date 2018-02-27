---
UID: NF:printoem.OEMBitBlt
title: OEMBitBlt function
author: windows-driver-content
description: The OEMBitBlt function provides general bit-block transfer capabilities between device-managed surfaces, between GDI-managed standard-format bitmaps, or between a device-managed surface and a GDI-managed standard-format bitmap.
old-location: print\oembitblt.htm
old-project: print
ms.assetid: d47e1bdb-2c91-4f73-b742-5312d989781a
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: OEMBitBlt, OEMBitBlt function [Print Devices], print.oembitblt, print_unidrv-pscript_rendering_972c744c-971c-423f-a4fe-92b87cef8094.xml, printoem/OEMBitBlt
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
-	OEMBitBlt
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMBitBlt function


## -description


The <code>OEMBitBlt</code> function provides general bit-block transfer capabilities between <a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">device-managed surfaces</a>, between GDI-managed standard-format bitmaps, or between a device-managed surface and a GDI-managed standard-format bitmap.


## -syntax


````
BOOL  APIENTRY OEMBitBlt(
   SURFOBJ  *psoTrg,
   SURFOBJ  *psoSrc,
   SURFOBJ  *psoMask,
   CLIPOBJ  *pco,
   XLATEOBJ *pxlo,
   RECTL    *prclTrg,
   POINTL   *pptlSrc,
   POINTL   *pptlMask,
   BRUSHOBJ *pbo,
   POINTL   *pptlBrush,
   ROP4     rop4
);
````


## -parameters




### -param psoTrg


### -param psoSrc


### -param psoMask


### -param pco


### -param pxlo


### -param prclTrg


### -param pptlSrc


### -param pptlMask


### -param pbo


### -param pptlBrush


### -param rop4

