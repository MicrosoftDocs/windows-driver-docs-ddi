---
UID: NF:printoem.OEMPlgBlt
title: OEMPlgBlt function
author: windows-driver-content
description: The OEMPlgBlt function provides rotate bit-block transfer capabilities between combinations of device-managed and GDI-managed surfaces.
old-location: print\oemplgblt.htm
old-project: print
ms.assetid: c33a9592-8e1b-4028-bd34-72cc4885f17f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: OEMPlgBlt, OEMPlgBlt function [Print Devices], print.oemplgblt, print_unidrv-pscript_rendering_b0052697-f944-4969-94c3-efc74838d571.xml, printoem/OEMPlgBlt
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMPlgBlt
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMPlgBlt function


## -description


The <code>OEMPlgBlt</code> function provides rotate bit-block transfer capabilities between combinations of device-managed and GDI-managed surfaces.


## -syntax


````
BOOL APIENTRY OEMPlgBlt(
   SURFOBJ         *psoDst,
   SURFOBJ         *psoSrc,
   SURFOBJ         *psoMask,
   CLIPOBJ         *pco,
   XLATEOBJ        *pxlo,
   COLORADJUSTMENT *pca,
   POINTL          *pptlBrushOrg,
   POINTFIX        *pptfixDest,
   RECTL           *prclSrc,
   POINTL          *pptlMask,
   ULONG           iMode
);
````


## -parameters




### -param psoDst


### -param psoSrc


### -param psoMask


### -param pco


### -param pxlo


### -param pca


### -param pptlBrushOrg


### -param pptfixDest


### -param prclSrc


### -param pptlMask


### -param iMode

