---
UID: NF:printoem.OEMPaint
title: OEMPaint function (printoem.h)
description: The OEMPaint function is obsolete, and is no longer called by GDI in Windows 2000 and later. See DrvPaint.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMPaint function"]
ms.keywords: OEMPaint, OEMPaint function [Print Devices], print.oempaint, print_unidrv-pscript_rendering_c9624a47-02fd-4eba-80d9-4035713ac594.xml, printoem/OEMPaint
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
 - OEMPaint
 - printoem/OEMPaint
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMPaint
---

## -description

The **OEMPaint** function is obsolete, and is no longer called by GDI in Windows 2000 and later. See [DrvPaint](/windows/win32/api/winddi/nf-winddi-drvpaint).

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pbo

Defines the **BRUSHOBJ** parameter *pbo*.

### -param pptlBrushOrg

Defines the **POINTL** parameter *pptlBrushOrg*.

### -param mix

Defines the **MIX** parameter *mix*.

## -returns

Returns a **BOOL** value.

## -remarks

If you call into the core driver, cast the call using the **PFN_DrvPaint** function pointer.
