---
UID: NF:printoem.OEMSendPage
title: OEMSendPage function (printoem.h)
description: The OEMSendPage function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.
old-location: print\oemsendpage.htm
tech.root: print
ms.assetid: 9a3380d0-2d90-49ec-b97d-be55eb6eaaa5
ms.date: 04/20/2018
keywords: ["OEMSendPage function"]
ms.keywords: OEMSendPage, OEMSendPage function [Print Devices], print.oemsendpage, print_unidrv-pscript_rendering_6a896dea-57aa-4fa0-810f-dadb79b13079.xml, printoem/OEMSendPage
f1_keywords:
 - "printoem/OEMSendPage"
 - "OEMSendPage"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- OEMSendPage
product:
- Windows
targetos: Windows
req.typenames: 
---

# OEMSendPage function


## -description


The <code>OEMSendPage</code> function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.


## -parameters




### -param pso

