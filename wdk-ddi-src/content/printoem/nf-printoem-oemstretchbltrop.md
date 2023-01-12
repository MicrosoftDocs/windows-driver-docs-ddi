---
UID: NF:printoem.OEMStretchBltROP
title: OEMStretchBltROP function (printoem.h)
description: The OEMStretchBltROP function performs a stretching bit-block transfer using a raster operation (ROP).
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMStretchBltROP function"]
ms.keywords: OEMStretchBltROP, OEMStretchBltROP function [Print Devices], print.oemstretchbltrop, print_unidrv-pscript_rendering_b1617a87-83e0-4b49-b123-e1db1ed3dd70.xml, printoem/OEMStretchBltROP
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
 - OEMStretchBltROP
 - printoem/OEMStretchBltROP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMStretchBltROP
---

## -description

The **OEMStretchBltROP** function performs a stretching bit-block transfer using a [raster operation (ROP)](/windows-hardware/drivers/).

## -parameters

### -param psoDest

Defines the **SURFOBJ** parameter *psoDest*.

### -param psoSrc

Defines the **SURFOBJ** parameter *psoSrc*.

### -param psoMask

Defines the **SURFOBJ** parameter *psoMask*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param pca

Defines the **COLORADJUSTMENT** parameter *pca*.

### -param pptlHTOrg

Defines the **POINTL** parameter *pptlHTOrg*.

### -param prclDest

Defines the **RECTL** parameter *prclDest*.

### -param prclSrc

Defines the **RECTL** parameter *prclSrc*.

### -param pptlMask

Defines the **POINTL** parameter *pptlMask*.

### -param iMode

Defines the **ULONG** parameter *iMode*.

### -param pbo

Defines the **BRUSHOBJ** parameter *pbo*.

### -param rop4

Defines the **ROP4** parameter *rop4*.

## -returns

Returns a **BOOL** value.
