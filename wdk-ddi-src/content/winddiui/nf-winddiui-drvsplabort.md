---
UID: NF:winddiui.DrvSplAbort
title: DrvSplAbort function (winddiui.h)
description: 
old-location: print\drvsplabort.htm
tech.root: print
ms.assetid: b40dff76-4330-4527-b1f6-69f625732604
ms.date: 04/20/2018
ms.keywords: DrvSplAbort, DrvSplAbort function [Print Devices], print.drvsplabort, print_interface-graphics_78bb32ad-7688-4ea9-9369-93db9d2eea96.xml, winddiui/DrvSplAbort
ms.topic: function
req.header: winddiui.h
req.include-header: 
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winddiui.h
api_name:
-	DrvSplAbort
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvSplAbort function


## -description





## -parameters




### -param hDriver


## -returns



This function does not return a value.

<h2><a id="ddk_drvsplabort_gg"></a><a id="DDK_DRVSPLABORT_GG"></a></h2>
The <b>DrvSplAbort</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff548544">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplAbort</b> function enables a user-mode rendering DLL to respond to a request to cancel a print job.

<h3><a id="comments"></a><a id="COMMENTS"></a>Comments</h3>
To supply user-mode image-rendering code for printers, see <a href="https://msdn.microsoft.com/1e63d01e-8cf2-488a-89e8-d4a3ff5cfe19">Choosing User Mode or Kernel Mode</a>.



