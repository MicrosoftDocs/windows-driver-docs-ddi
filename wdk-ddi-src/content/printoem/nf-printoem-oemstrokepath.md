---
UID: NF:printoem.OEMStrokePath
title: OEMStrokePath function
author: windows-driver-content
description: The OEMStrokePath function strokes a path.
old-location: print\oemstrokepath.htm
old-project: print
ms.assetid: e761a8b4-729f-4f03-a4b4-2ed1b62ec012
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMStrokePath, OEMStrokePath function [Print Devices], print.oemstrokepath, print_unidrv-pscript_rendering_8bc38d91-34ed-4225-baf1-6ca18026b7d0.xml, printoem/OEMStrokePath
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
req.lib: 
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
-	OEMStrokePath
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStrokePath function


## -description


The <code>OEMStrokePath</code> function strokes a path.


## -syntax


````
BOOL APIENTRY OEMStrokePath(
   SURFOBJ   *pso,
   PATHOBJ   *ppo,
   CLIPOBJ   *pco,
   XFORMOBJ  *pxo,
   BRUSHOBJ  *pbo,
   POINTL    *pptlBrushOrg,
   LINEATTRS *plineattrs,
   MIX       mix
);
````


## -parameters




### -param pso


### -param ppo


### -param pco


### -param pxo


### -param pbo


### -param pptlBrushOrg


### -param plineattrs


### -param mix

