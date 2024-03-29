---
UID: NF:printoem.OEMStartPage
title: OEMStartPage function (printoem.h)
description: The OEMStartPage function is called by GDI when it is ready to start sending the contents of a physical page to the driver for rendering.
tech.root: print
ms.date: 08/11/2022
keywords: ["OEMStartPage function"]
ms.keywords: OEMStartPage, OEMStartPage function [Print Devices], print.oemstartpage, print_unidrv-pscript_rendering_df5731ee-40be-45e1-8dbb-b7893ec27622.xml, printoem/OEMStartPage
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
 - OEMStartPage
 - printoem/OEMStartPage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMStartPage
---

## -description

The **OEMStartPage** function is called by GDI when it is ready to start sending the contents of a physical page to the driver for rendering.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

## -returns

Returns a **BOOL** value.
