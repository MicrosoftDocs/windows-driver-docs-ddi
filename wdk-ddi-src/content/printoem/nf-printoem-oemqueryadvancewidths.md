---
UID: NF:printoem.OEMQueryAdvanceWidths
title: OEMQueryAdvanceWidths function (printoem.h)
description: The OEMQueryAdvanceWidths function returns character advance widths for a specified set of glyphs.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMQueryAdvanceWidths function"]
ms.keywords: OEMQueryAdvanceWidths, OEMQueryAdvanceWidths function [Print Devices], print.oemqueryadvancewidths, print_unidrv-pscript_rendering_14849fac-0d28-4961-b37b-ee14cd285018.xml, printoem/OEMQueryAdvanceWidths
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
 - OEMQueryAdvanceWidths
 - printoem/OEMQueryAdvanceWidths
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMQueryAdvanceWidths
---

## -description

The **OEMQueryAdvanceWidths** function returns character advance widths for a specified set of glyphs.

## -parameters

### -param dhpdev

Defines the **DHPDEV** parameter *dhpdev*.

### -param pfo

Defines the **FONTOBJ** parameter *pfo*.

### -param iMode

Defines the **ULONG** parameter *iMode*.

### -param phg [in]

Defines the **HGLYPH** parameter *phg*.

### -param pvWidths [out]

Defines the **PVOID** parameter *pvWidths*.

### -param cGlyphs

Defines the **ULONG** parameter *cGlyphs*.

## -returns

Returns a **BOOL** value.
