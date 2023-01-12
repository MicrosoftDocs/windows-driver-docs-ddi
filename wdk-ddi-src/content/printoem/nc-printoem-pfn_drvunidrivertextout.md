---
UID: NC:printoem.PFN_DrvUnidriverTextOut
title: PFN_DrvUnidriverTextOut (printoem.h)
description: The DrvUnidriverTextOut function is obsolete.
tech.root: print
ms.date: 08/11/2022
keywords: ["PFN_DrvUnidriverTextOut callback function"]
ms.keywords: PFN_DrvUnidriverTextOut, PFN_DrvUnidriverTextOut callback, PFN_DrvUnidriverTextOut callback function [Print Devices], print.drvunidrivertextout, print_obsoletefunctions_eeb13110-561c-4c0f-912b-1a3a1cebd846.xml, printoem/PFN_DrvUnidriverTextOut
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
 - PFN_DrvUnidriverTextOut
 - printoem/PFN_DrvUnidriverTextOut
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - PFN_DrvUnidriverTextOut
---

## -description

The **DrvUnidriverTextOut** function is obsolete.

Windows 2000 and later printer drivers should use [IPrintOemDriverUni::DrvUniTextOut](../prcomoem/nf-prcomoem-iprintoemdriveruni-drvunitextout.md).

This function pointer prototype defines the type of the **DrvUnidriverTextOut** member of the [DRVPROCS](./ns-printoem-_drvprocs.md) structure.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param pstro

Defines the **STROBJ** parameter *pstro*.

### -param pfo

Defines the **FONTOBJ** parameter *pfo*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param prclExtra

Defines the **RECTL** parameter *prclExtra*.

### -param prclOpaque

Defines the **RECTL** parameter *prclOpaque*.

### -param pboFore

Defines the **BRUSHOBJ** parameter *pboFore*.

### -param pboOpaque

Defines the **BRUSHOBJ** parameter *pboOpaque*.

### -param pptlBrushOrg

Defines the **POINTL** parameter *pptlBrushOrg*.

### -param mix

Defines the **MIX** parameter *mix*.

## -returns

Returns a **BOOL** value.