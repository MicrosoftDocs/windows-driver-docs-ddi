---
UID: NF:printoem.OEMTextOut
title: OEMTextOut function (printoem.h)
description: The OEMTextOut function calls for the driver to render a set of glyphs at specified positions.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMTextOut function"]
ms.keywords: OEMTextOut, OEMTextOut function [Print Devices], print.oemtextout, print_unidrv-pscript_rendering_fda6f01f-5d37-424f-aa4f-bf7849c50c19.xml, printoem/OEMTextOut
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
 - OEMTextOut
 - printoem/OEMTextOut
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMTextOut
---

## -description

The **OEMTextOut** function calls for the driver to render a set of glyphs at specified positions.

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

### -param pptlOrg

Defines the **POINTL** parameter *pptlOrg*.

### -param mix

Defines the **MIX** parameter *mix*.

## -returns

Returns a **BOOL** value.
