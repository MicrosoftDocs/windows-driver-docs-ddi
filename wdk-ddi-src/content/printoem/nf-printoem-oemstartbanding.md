---
UID: NF:printoem.OEMStartBanding
title: OEMStartBanding function
author: windows-driver-content
description: The OEMStartBanding function is called by GDI when it is ready to start sending bands of a physical page to the driver for rendering.
old-location: print\oemstartbanding.htm
old-project: print
ms.assetid: dc9a1cf4-89d5-46d4-b914-1bc8368d3a42
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMStartBanding
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
req.alt-api: OEMStartBanding
req.alt-loc: Printoem.h
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

# OEMStartBanding function



## -description
The <code>OEMStartBanding</code> function is called by GDI when it is ready to start sending bands of a physical page to the driver for rendering.



## -syntax

````
BOOL APIENTRY OEMStartBanding(
   SURFOBJ *pso,
   POINTL  *pptl
);
````


## -parameters

### -param pso 


### -param pptl 


## -remarks
