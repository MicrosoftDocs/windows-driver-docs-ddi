---
UID: NF:printoem.OEMCopyBits
title: OEMCopyBits function
author: windows-driver-content
description: The OEMCopyBits function performs translations between device-managed raster surfaces and GDI standard-format bitmaps.
old-location: print\oemcopybits.htm
old-project: print
ms.assetid: bd7a8fc6-0d68-4d80-b622-90cd981f9d13
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: printoem/OEMCopyBits, print_unidrv-pscript_rendering_fbf15e40-01e8-4207-b130-b152a225025e.xml, OEMCopyBits, OEMCopyBits function [Print Devices], print.oemcopybits
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
-	OEMCopyBits
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMCopyBits function


## -description


The <code>OEMCopyBits</code> function performs translations between device-managed raster surfaces and GDI standard-format bitmaps. 


## -syntax


````
BOOL  APIENTRY OEMCopyBits(
   SURFOBJ  *psoDest,
   SURFOBJ  *psoSrc,
   CLIPOBJ  *pco,
   XLATEOBJ *pxlo,
   RECTL    *prclDest,
   POINTL   *pptlSrc
);
````


## -parameters




### -param psoDest



### -param psoSrc



### -param pco



### -param pxlo



### -param prclDest



### -param pptlSrc


