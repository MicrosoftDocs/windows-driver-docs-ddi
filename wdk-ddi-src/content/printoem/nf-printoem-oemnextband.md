---
UID: NF:printoem.OEMNextBand
title: OEMNextBand function
author: windows-driver-content
description: The OEMNextBand function is called by GDI when it has finished drawing a band for a physical page, so that the driver can send the band to the printer.
old-location: print\oemnextband.htm
old-project: print
ms.assetid: 547af6b1-63cf-4e61-a357-1a7fdc33e43c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: OEMNextBand, print_unidrv-pscript_rendering_db168f2e-09ab-4c1d-9a68-970af445e128.xml, print.oemnextband, OEMNextBand function [Print Devices], printoem/OEMNextBand
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
-	OEMNextBand
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMNextBand function


## -description


The <code>OEMNextBand</code> function is called by GDI when it has finished drawing a band for a physical page, so that the driver can send the band to the printer.


## -syntax


````
BOOL APIENTRY OEMNextBand(
   SURFOBJ *pso,
   POINTL  *pptl
);
````


## -parameters




### -param pso


### -param pptl

