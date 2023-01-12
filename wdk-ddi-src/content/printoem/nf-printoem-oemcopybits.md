---
UID: NF:printoem.OEMCopyBits
title: OEMCopyBits function (printoem.h)
description: The OEMCopyBits function performs translations between device-managed raster surfaces and GDI standard-format bitmaps.
tech.root: print
ms.date: 08/08/2022
keywords: ["OEMCopyBits function"]
ms.keywords: OEMCopyBits, OEMCopyBits function [Print Devices], print.oemcopybits, print_unidrv-pscript_rendering_fbf15e40-01e8-4207-b130-b152a225025e.xml, printoem/OEMCopyBits
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
 - OEMCopyBits
 - printoem/OEMCopyBits
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMCopyBits
---

## -description

The **OEMCopyBits** function performs translations between device-managed raster surfaces and GDI standard-format bitmaps.

## -parameters

### -param psoDest

Defines the **SURFOBJ** parameter *psoDest*.

### -param psoSrc

Defines the **SURFOBJ** parameter *psoSrc*.

### -param pco

Defines the **CLIPOBJ** parameter *pco*.

### -param pxlo

Defines the **XLATEOBJ** parameter *pxlo*.

### -param prclDest

Defines the **RECTL** parameter *prclDest*.

### -param pptlSrc

Defines the **POINTL** parameter *pptlSrc*.

## -returns

Returns a **BOOL** value.
