---
UID: NF:winddiui.DrvSplAbort
title: DrvSplAbort function
author: windows-driver-content
description: .
old-location: print\drvsplabort.htm
old-project: print
ms.assetid: b40dff76-4330-4527-b1f6-69f625732604
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: DrvSplAbort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvSplAbort
req.alt-loc: winddiui.h
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
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvSplAbort function



## -description




## -syntax

````
VOID WINAPI DrvSplAbort(
   HANDLE hDriver
);
````


## -parameters

### -param hDriver 


## -returns
This function does not return a value.

The <b>DrvSplAbort</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplAbort</b> function enables a user-mode rendering DLL to respond to a request to cancel a print job.

To supply user-mode image-rendering code for printers, see <a href="https://msdn.microsoft.com/1e63d01e-8cf2-488a-89e8-d4a3ff5cfe19">Choosing User Mode or Kernel Mode</a>.


## -remarks
