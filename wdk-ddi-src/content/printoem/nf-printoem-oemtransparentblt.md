---
UID: NF:printoem.OEMTransparentBlt
title: OEMTransparentBlt function (printoem.h)
description: The OEMTransparentBlt function provides bit-block transfer capabilities with transparency.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMTransparentBlt function"]
ms.keywords: OEMTransparentBlt, OEMTransparentBlt function [Print Devices], print.oemtransparentblt, print_unidrv-pscript_rendering_a02993f9-58d7-4a42-ad7b-be61bd6b265d.xml, printoem/OEMTransparentBlt
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
 - OEMTransparentBlt
 - printoem/OEMTransparentBlt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMTransparentBlt
---

## -description

The **OEMTransparentBlt** function provides bit-block transfer capabilities with transparency.

## -parameters

### -param psoDst

Defines the **SURFOBJ** parameter *psoDst*.

### -param psoSrc

Defines the **SURFOBJ** parameter *psoSrc*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param prclDst

Defines the **RECTL** parameter *prclDst*.

### -param prclSrc

Defines the **RECTL** parameter *prclSrc*.

### -param iTransColor

Defines the **ULONG** parameter *iTransColor*.

### -param ulReserved

Defines the **ULONG** parameter *ulReserved*.

## -returns

Returns a **BOOL** value.
