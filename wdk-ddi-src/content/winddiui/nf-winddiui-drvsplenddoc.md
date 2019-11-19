---
UID: NF:winddiui.DrvSplEndDoc
title: DrvSplEndDoc function (winddiui.h)
description: The DrvSplEndDoc function is obsolete.
old-location: print\drvsplenddoc.htm
tech.root: print
ms.assetid: 7972fd88-ca99-4a42-8476-754b26eb118c
ms.date: 11/18/2019
ms.keywords: DrvSplEndDoc, DrvSplEndDoc function [Print Devices], print.drvsplenddoc, print_interface-graphics_13e407aa-2d2a-4ec5-b3ab-bcb6fa745039.xml, winddiui/DrvSplEndDoc
ms.topic: function
f1_keywords:
 - "winddiui/DrvSplEndDoc"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winddiui.h
api_name:
- DrvSplEndDoc
product:
- Windows
targetos: Windows
req.typenames: 
---

# DrvSplEndDoc function

## -description

The **DrvSplEndDoc** function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later.

Use [DrvDocumentEvent](https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentevent) instead of this function.

The **DrvSplEndDoc** function enables a user-mode rendering DLL to perform operations associated with the end of a print job.

## -parameters

### -param hDriver

The handle of the driver object.

## -remarks

To supply user-mode image-rendering code for printers, see [Choosing User Mode or Kernel Mode](https://docs.microsoft.com/windows-hardware/drivers/print/choosing-user-mode-or-kernel-mode).
