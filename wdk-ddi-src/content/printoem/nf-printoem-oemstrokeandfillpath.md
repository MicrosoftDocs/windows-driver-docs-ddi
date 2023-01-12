---
UID: NF:printoem.OEMStrokeAndFillPath
title: OEMStrokeAndFillPath function (printoem.h)
description: The OEMStrokeAndFillPath function concurrently strokes and fills a path.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMStrokeAndFillPath function"]
ms.keywords: OEMStrokeAndFillPath, OEMStrokeAndFillPath function [Print Devices], print.oemstrokeandfillpath, print_unidrv-pscript_rendering_e370d4e7-4593-46c7-87dd-93c963400290.xml, printoem/OEMStrokeAndFillPath
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
 - OEMStrokeAndFillPath
 - printoem/OEMStrokeAndFillPath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMStrokeAndFillPath
---

## -description

The **OEMStrokeAndFillPath** function concurrently strokes and fills a path.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param ppo

Defines the **PATHOBJ** parameter *ppo*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxo

Defines the **XFORMOBJ** parameter *pxo*.

### -param pboStroke

Defines the **BRUSHOBJ** parameter *pboStroke*.

### -param plineattrs

Defines the **LINEATTRS** parameter *plineattrs*.

### -param pboFill

Defines the **BRUSHOBJ** parameter *pboFill*.

### -param pptlBrushOrg

Defines the **POINTL** parameter *pptlBrushOrg*.

### -param mixFill

Defines the **MIX** parameter *mixFill*.

### -param flOptions

Defines the **FLONG** parameter *flOptions*.

## -returns

Returns a **BOOL** value.
