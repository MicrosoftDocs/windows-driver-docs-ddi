---
UID: NF:printoem.OEMDitherColor
title: OEMDitherColor function (printoem.h)
description: The OEMDitherColor function requests the device to create a brush dithered against a device palette.
tech.root: print
ms.date: 08/08/2022
keywords: ["OEMDitherColor function"]
ms.keywords: OEMDitherColor, OEMDitherColor function [Print Devices], print.oemdithercolor, print_unidrv-pscript_rendering_e220d80f-83d4-4f4a-9fdc-ca25b48dd718.xml, printoem/OEMDitherColor
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
targetos: Windows
req.typenames: 
f1_keywords:
 - OEMDitherColor
 - printoem/OEMDitherColor
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMDitherColor
---

## -description

The **OEMDitherColor** function requests the device to create a brush dithered against a device palette.

## -parameters

### -param dhpdev

Defines the **DHPDEV** parameter *dhpdev*.

### -param iMode

Defines the **ULONG** parameter *iMode*.

### -param rgbColor

Defines the **ULONG** parameter *rgbColor*.

### -param pulDither

Defines the **ULONG** parameter *pulDither*.

## -returns

Returns a **ULONG** value.
