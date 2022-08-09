---
UID: NF:printoem.OEMBitBlt
title: OEMBitBlt function (printoem.h)
description: The OEMBitBlt function provides general bit-block transfer capabilities between device-managed surfaces, between GDI-managed standard-format bitmaps, or between a device-managed surface and a GDI-managed standard-format bitmap.
tech.root: print
ms.date: 08/05/2022
keywords: ["OEMBitBlt function"]
ms.keywords: OEMBitBlt, OEMBitBlt function [Print Devices], print.oembitblt, print_unidrv-pscript_rendering_972c744c-971c-423f-a4fe-92b87cef8094.xml, printoem/OEMBitBlt
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
 - OEMBitBlt
 - printoem/OEMBitBlt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMBitBlt
---

## -description

The **OEMBitBlt**** function provides general bit-block transfer capabilities between device-managed surfaces, between GDI-managed standard-format bitmaps, or between a device-managed surface and a GDI-managed standard-format bitmap.

## -parameters

### -param psoTrg

Defines the **SURFOBJ** parameter *psoTrg*.

### -param psoSrc

Defines the **SURFOBJ** parameter *psoSrc*.

### -param psoMask

Defines the **SURFOBJ** parameter *psoMask*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param prclTrg

Defines the **RECTL** parameter *prclTrg*.

### -param pptlSrc

Defines the **POINTL** parameter *pptlSrc*.

### -param pptlMask

Defines the **POINTL** parameter *pptlMask*.

### -param pbo

Defines the **BRUSHOBJ** parameter *pbo*.

### -param pptlBrush

Defines the **POINTL** parameter *pptlBrush*.

### -param rop4

Defines the **ROP4** parameter *rop4*.

## -returns

Returns a **BOOL** value.
