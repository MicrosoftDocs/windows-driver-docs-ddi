---
UID: NF:printoem.OEMStartPage
title: OEMStartPage function
author: windows-driver-content
description: The OEMStartPage function is called by GDI when it is ready to start sending the contents of a physical page to the driver for rendering.
old-location: print\oemstartpage.htm
old-project: print
ms.assetid: 86cee994-2dfe-4eaf-906b-ce6d9051399e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: OEMStartPage, OEMStartPage function [Print Devices], print.oemstartpage, print_unidrv-pscript_rendering_df5731ee-40be-45e1-8dbb-b7893ec27622.xml, printoem/OEMStartPage
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMStartPage
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStartPage function


## -description


The <code>OEMStartPage</code> function is called by GDI when it is ready to start sending the contents of a physical page to the driver for rendering.


## -syntax


````
BOOL APIENTRY OEMStartPage(
   SURFOBJ *pso
);
````


## -parameters




### -param pso

