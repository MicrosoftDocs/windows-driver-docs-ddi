---
UID: NF:printoem.OEMStretchBlt
title: OEMStretchBlt function (printoem.h)
description: The OEMStretchBlt function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMStretchBlt function"]
ms.keywords: OEMStretchBlt, OEMStretchBlt function [Print Devices], print.oemstretchblt, print_unidrv-pscript_rendering_cbbd51bd-2201-4fd4-9b3e-1e86f3962be8.xml, printoem/OEMStretchBlt
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
 - OEMStretchBlt
 - printoem/OEMStretchBlt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMStretchBlt
---

## -description

The **OEMStretchBlt** function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces.

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

## -returns

Returns a **BOOL** value.
