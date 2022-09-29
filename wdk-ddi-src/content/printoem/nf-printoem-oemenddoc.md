---
UID: NF:printoem.OEMEndDoc
title: OEMEndDoc function (printoem.h)
description: The OEMEndDoc function is called by the GDI when it has finished sending a document to the driver for rendering.
tech.root: print
ms.date: 08/08/2022
keywords: ["OEMEndDoc function"]
ms.keywords: OEMEndDoc, OEMEndDoc function [Print Devices], print.oemenddoc, print_unidrv-pscript_rendering_1b17db2b-0ea4-4acb-9130-bbc7fe3a0b4a.xml, printoem/OEMEndDoc
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
 - OEMEndDoc
 - printoem/OEMEndDoc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMEndDoc
---

## -description

The **OEMEndDoc** function is called by the GDI when it has finished sending a document to the driver for rendering.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param fl

Defines the **FLONG** parameter *f1*.

## -returns

Returns a **BOOL** value.
