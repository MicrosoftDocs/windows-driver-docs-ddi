---
UID: NF:printoem.OEMFillPath
title: OEMFillPath function (printoem.h)
description: The OEMFillPath function handles the filling of closed paths.
tech.root: print
ms.date: 08/09/2022
keywords: ["OEMFillPath function"]
ms.keywords: OEMEscape, OEMEscape function [Print Devices], OEMFillPath, print.oemfillpath, print_unidrv-pscript_rendering_0c8783bf-0e73-4b66-98a2-b71ee177549b.xml, printoem/OEMEscape
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
 - OEMFillPath
 - printoem/OEMFillPath
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMFillPath
---

## -description

The **OEMFillPath** function handles the filling of closed paths.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param ppo

Defines the **PATHOBJ** parameter *ppo*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pbo

Defines the **BRUSHOBJ** parameter *pbo*.

### -param pptlBrushOrg

Defines the **POINTL** parameter *pptlBrushOrg*.

### -param mix

Defines the **MIX** parameter *mix*.

### -param flOptions

Defines the **FLONG** parameter *flOptions*.

## -returns

Returns a **BOOL** value.
