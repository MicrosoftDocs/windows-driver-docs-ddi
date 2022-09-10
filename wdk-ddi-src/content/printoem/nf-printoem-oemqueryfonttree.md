---
UID: NF:printoem.OEMQueryFontTree
title: OEMQueryFontTree function (printoem.h)
description: The OEMQueryFontTree function provides GDI with a pointer to a structure that defines mapping of glyph and kerning handles.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMQueryFontTree function"]
ms.keywords: OEMQueryFontTree, OEMQueryFontTree function [Print Devices], print.oemqueryfonttree, print_unidrv-pscript_rendering_f069b851-3104-4cca-8902-d844350a719e.xml, printoem/OEMQueryFontTree
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
 - OEMQueryFontTree
 - printoem/OEMQueryFontTree
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - printoem.h
api_name:
 - OEMQueryFontTree
---

## -description

The **OEMQueryFontTree** function provides GDI with a pointer to a structure that defines one of the following:

- A mapping from Unicode to glyph handles, including glyph variants

- A mapping of kerning pairs to kerning handles

## -parameters

### -param dhpdev

Defines the **DHPDEV** parameter *dhpdev*.

### -param iFile

Defines the **ULONG_PTR** parameter *iFile*.

### -param iFace

Defines the **ULONG** parameter *iFace*.

### -param iMode

Defines the **ULONG** parameter *iMode*.

### -param pid

Defines the **ULONG_PTR** parameter *pid*.

## -returns

Returns a **PVOID** value.
