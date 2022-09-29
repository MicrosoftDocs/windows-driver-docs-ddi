---
UID: NF:printoem.OEMGradientFill
title: OEMGradientFill function (printoem.h)
description: The OEMGradientFill function shades the specified primitives.
tech.root: print
ms.date: 08/09/2022
keywords: ["OEMGradientFill function"]
ms.keywords: OEMGradientFill, OEMGradientFill function [Print Devices], print.oemgradientfill, print_unidrv-pscript_rendering_ddb279ca-c526-4993-94ce-cf8caa0febb4.xml, printoem/OEMGradientFill
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
 - OEMGradientFill
 - printoem/OEMGradientFill
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMGradientFill
---

## -description

The **OEMGradientFill** function shades the specified primitives.

## -parameters

### -param psoDest

Defines the **SURFOBJ** parameter *psoDest*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param pVertex

Defines the **TRIVERTEX** parameter *pVertex*.

### -param nVertex

Defines the **ULONG** parameter *nVertex*.

### -param pMesh

Defines the **PVOID** parameter *pMesh*.

### -param nMesh

Defines the **ULONG** parameter *nMesh*.

### -param prclExtents

Defines the **RECTL** parameter *prclExtents*.

### -param pptlDitherOrg

Defines the **POINTL** parameter *pptlDitherOrg*.

### -param ulMode

Defines the **ULONG** parameter *ulMode*.

## -returns

Returns a **BOOL** value.
