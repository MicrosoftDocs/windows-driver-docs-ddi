---
UID: NF:printoem.OEMStartDoc
title: OEMStartDoc function
author: windows-driver-content
description: The OEMStartDoc function is called by GDI when it is ready to start sending a document to the driver for rendering.
old-location: print\oemstartdoc.htm
old-project: print
ms.assetid: 67580632-ff9a-4d29-8e4e-c21f04aa4b47
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print_unidrv-pscript_rendering_728069a7-4d66-4a83-a1e2-949557157d71.xml, OEMStartDoc, print.oemstartdoc, printoem/OEMStartDoc, OEMStartDoc function [Print Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	OEMStartDoc
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStartDoc function


## -description


The <code>OEMStartDoc</code> function is called by GDI when it is ready to start sending a document to the driver for rendering.


## -syntax


````
BOOL APIENTRY OEMStartDoc(
       SURFOBJ *pso,
  _In_ PWSTR   pwszDocName,
       DWORD   dwJobId
);
````


## -parameters




### -param pso


### -param pwszDocName [in]


### -param dwJobId

