---
UID: NF:printoem.OEMPlgBlt
title: OEMPlgBlt function (printoem.h)
description: The OEMPlgBlt function provides rotate bit-block transfer capabilities between combinations of device-managed and GDI-managed surfaces.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMPlgBlt function"]
ms.keywords: OEMPlgBlt, OEMPlgBlt function [Print Devices], print.oemplgblt, print_unidrv-pscript_rendering_b0052697-f944-4969-94c3-efc74838d571.xml, printoem/OEMPlgBlt
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
 - OEMPlgBlt
 - printoem/OEMPlgBlt
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMPlgBlt
---

## -description

The **OEMPlgBlt** function provides rotate bit-block transfer capabilities between combinations of device-managed and GDI-managed surfaces.

## -parameters

### -param psoDst

Defines the **SURFOBJ** parameter *psoDst*.

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

### -param pptlBrushOrg

Defines the **POINTL** parameter *pptlBrushOrg*.

### -param pptfixDest

Defines the **POINTFIX** parameter *pptfixDest*.

### -param prclSrc

Defines the **RECTL** parameter *prclSrc*.

### -param pptlMask

Defines the **POINTL** parameter *pptlMask*.

### -param iMode

Defines the **ULONG** parameter *iMode*.

## -returns

Returns a **BOOL** value.
