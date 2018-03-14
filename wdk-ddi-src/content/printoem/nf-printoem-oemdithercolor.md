---
UID: NF:printoem.OEMDitherColor
title: OEMDitherColor function
author: windows-driver-content
description: The OEMDitherColor function requests the device to create a brush dithered against a device palette.
old-location: print\oemdithercolor.htm
old-project: print
ms.assetid: bf8c2140-8917-42af-86bf-c2f25b0c42b7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMDitherColor, OEMDitherColor function [Print Devices], print.oemdithercolor, print_unidrv-pscript_rendering_e220d80f-83d4-4f4a-9fdc-ca25b48dd718.xml, printoem/OEMDitherColor
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
-	OEMDitherColor
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMDitherColor function


## -description


The <code>OEMDitherColor</code> function requests the device to create a brush dithered against a device palette.


## -syntax


````
ULONG APIENTRY OEMDitherColor(
   DHPDEV dhpdev,
   ULONG  iMode,
   ULONG  rgbColor,
   ULONG  *pulDither
);
````


## -parameters




### -param dhpdev


### -param iMode


### -param rgbColor


### -param pulDither

