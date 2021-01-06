---
UID: NF:winddiui.DrvSplClose
title: DrvSplClose function (winddiui.h)
description: The DrvSplClose function is obsolete.
old-location: print\drvsplclose.htm
tech.root: print
ms.date: 11/18/2019
keywords: ["DrvSplClose function"]
ms.keywords: DrvSplClose, DrvSplClose function [Print Devices], print.drvsplclose, print_interface-graphics_e43f66ed-0e5e-4a27-ad52-0faebe549ac5.xml, winddiui/DrvSplClose
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
 - DrvSplClose
 - winddiui/DrvSplClose
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winddiui.h
api_name:
 - DrvSplClose
---

# DrvSplClose function


## -description

The **DrvSplClose** function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later.

Use [DrvDocumentEvent](./nf-winddiui-drvdocumentevent.md) instead of this function.

The **DrvSplClose** function enables a user-mode rendering DLL to deallocate resources.

## -parameters

### -param hDriver

The handle of the driver object.

## -remarks

To supply user-mode image-rendering code for printers, see [Choosing User Mode or Kernel Mode](/windows-hardware/drivers/print/choosing-user-mode-or-kernel-mode).
