---
UID: NF:printoem.OEMEnablePDEV
title: OEMEnablePDEV function (printoem.h)
description: Describes the OEMEnablePDEV function.
tech.root: print
ms.date: 08/08/2022
keywords: ["OEMEnablePDEV function"]
ms.keywords: OEMEnablePDEV, OEMEnablePDEV function [Print Devices], print.oemenablepdev, print_obsoletefunctions_f6d0b164-0458-442f-ac6a-791592883196.xml, printoem/OEMEnablePDEV
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
 - OEMEnablePDEV
 - printoem/OEMEnablePDEV
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMEnablePDEV
---

## -description

Describes the **OEMEnablePDEV** function.

## -parameters

### -param pdevobj

Defines the **PDEVOBJ** parameter *pdevobj*.

### -param pPrinterName [in]

Defines the **PWSTR** parameter *pPrinterName*.

### -param cPatterns

Defines the **ULONG** parameter *cPatterns*.

### -param phsurfPatterns [in]

Defines the **HSURF** parameter *phsurfPatterns*.

### -param cjGdiInfo

Defines the **ULONG** parameter *cjGdiInfo*.

### -param pGdiInfo [in, out]

Defines the **GDIINFO** parameter *pGdiInfo*.

### -param cjDevInfo

Defines the **ULONG** parameter *cjDevInfo*.

### -param pDevInfo [in, out]

Defines the **DEVINFO** parameter *pDevInfo*.

### -param pded [in]

Defines the **DRVENABLEDATA** parameter *pded*.

## -returns

Returns a **PDEVOEM** value.
