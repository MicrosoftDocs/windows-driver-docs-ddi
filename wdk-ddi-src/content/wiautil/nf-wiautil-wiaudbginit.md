---
UID: NF:wiautil.wiauDbgInit
title: wiauDbgInit macro (wiautil.h)
description: The wiauDbgInit function initializes WIA debugging.
old-location: image\wiaudbginit.htm
tech.root: image
ms.assetid: a9308d66-c8b0-4e0e-8203-e2b3f91b7e27
ms.date: 05/03/2018
ms.keywords: image.wiaudbginit, wiauDbgInit, wiauDbgInit function [Imaging Devices], wiauFncs_0f18edab-cbf7-4012-85ea-93f101343ecb.xml, wiautil/wiauDbgInit
f1_keywords:
 - "wiautil/wiauDbgInit"
req.header: wiautil.h
req.include-header: Wiautil.h
req.target-type: Desktop
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
- wiautil.h
api_name:
- wiauDbgInit
product:
- Windows
targetos: Windows
req.typenames: 
---

# wiauDbgInit macro

## -description

The **wiauDbgInit** function initializes WIA debugging.

## -parameters

### -param a

- **hInstance [in, optional]** - Is the handle to the DLL instance.

## -remarks

If the **wiauDbgInit** function not called, all DLLs loaded by a process inherit the debug flags of that process.
