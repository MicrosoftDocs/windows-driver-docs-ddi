---
UID: NF:printoem.OEMStartDoc
title: OEMStartDoc function (printoem.h)
description: The OEMStartDoc function is called by GDI when it is ready to start sending a document to the driver for rendering.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMStartDoc function"]
ms.keywords: OEMStartDoc, OEMStartDoc function [Print Devices], print.oemstartdoc, print_unidrv-pscript_rendering_728069a7-4d66-4a83-a1e2-949557157d71.xml, printoem/OEMStartDoc
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
 - OEMStartDoc
 - printoem/OEMStartDoc
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMStartDoc
---

## -description

The **OEMStartDoc** function is called by GDI when it is ready to start sending a document to the driver for rendering.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

### -param pwszDocName [in]

Defines the **PWSTR** parameter *pwszDocName*.

### -param dwJobId

Defines the **DWORD** parameter *dwJobId*.

## -returns

Returns a **BOOL** value.
