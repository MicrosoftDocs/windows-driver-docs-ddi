---
UID: NF:printoem.OEMSendPage
title: OEMSendPage function (printoem.h)
description: The OEMSendPage function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.
tech.root: print
ms.date: 08/10/2022
keywords: ["OEMSendPage function"]
ms.keywords: OEMSendPage, OEMSendPage function [Print Devices], print.oemsendpage, print_unidrv-pscript_rendering_6a896dea-57aa-4fa0-810f-dadb79b13079.xml, printoem/OEMSendPage
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
 - OEMSendPage
 - printoem/OEMSendPage
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - OEMSendPage
---

## -description

The **OEMSendPage** function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.

## -parameters

### -param pso

Defines the **SURFOBJ** parameter *pso*.

## -returns

Returns a **BOOL** value.
