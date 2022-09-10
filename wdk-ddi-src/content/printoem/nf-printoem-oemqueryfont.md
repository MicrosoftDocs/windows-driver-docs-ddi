---
UID: NF:printoem.OEMQueryFont
title: OEMQueryFont function (printoem.h)
description: The OEMQueryFont function is used by GDI to get the IFIMETRICS structure for a given font.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMQueryFont function"]
ms.keywords: OEMQueryFont, OEMQueryFont function [Print Devices], print.oemqueryfont, print_unidrv-pscript_rendering_52b50b2d-ab61-420f-be04-7285a5504be6.xml, printoem/OEMQueryFont
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
 - OEMQueryFont
 - printoem/OEMQueryFont
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMQueryFont
---

## -description

The **OEMQueryFont** function is used by GDI to get the [IFIMETRICS](/windows/win32/api/winddi/ns-winddi-ifimetrics) structure for a given font.

## -parameters

### -param dhpdev

Defines the **DHPDEV** parameter *dhpdev*.

### -param iFile

Defines the **ULONG_PTR** parameter *iFile*.

### -param iFace

Defines the **ULONG** parameter *iFace*.

### -param pid

Defines the **ULONG_PTR** parameter *pid*.

## -returns

Returns a **PIFIMETRICS** value.
