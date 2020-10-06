---
UID: NF:winddiui.DrvSplAbort
title: DrvSplAbort function (winddiui.h)
description: The DrvSplAbort function is obsolete.
old-location: print\drvsplabort.htm
tech.root: print
ms.assetid: b40dff76-4330-4527-b1f6-69f625732604
ms.date: 11/18/2019
keywords: ["DrvSplAbort function"]
ms.keywords: DrvSplAbort, DrvSplAbort function [Print Devices], print.drvsplabort, print_interface-graphics_78bb32ad-7688-4ea9-9369-93db9d2eea96.xml, winddiui/DrvSplAbort
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
targetos: Windows
req.typenames: 
f1_keywords:
 - DrvSplAbort
 - winddiui/DrvSplAbort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvSplAbort
---

# DrvSplAbort function


## -description

The **DrvSplAbort** function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later.

Use [DrvDocumentEvent](./nf-winddiui-drvdocumentevent.md) instead of this function.

The **DrvSplAbort** function enables a user-mode rendering DLL to respond to a request to cancel a print job.

## -parameters

### -param hDriver

The handle of the driver object.

## -remarks

To supply user-mode image-rendering code for printers, see [Choosing User Mode or Kernel Mode](/windows-hardware/drivers/print/choosing-user-mode-or-kernel-mode).