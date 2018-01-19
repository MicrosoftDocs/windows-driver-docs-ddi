---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK
title: PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK
author: windows-driver-content
description: The ReconstructStack callback function queries dump stream provider on a per-thread basis.
old-location: debugger\reconstructstack.htm
old-project: debugger
ms.assetid: 639A90E8-4B2D-413B-B6F9-078C9DF1B02F
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DOT4_ACTIVITY, *PDOT4_ACTIVITY, DOT4_ACTIVITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ReconstructStack
req.alt-loc: Dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK callback



## -description
The <i>ReconstructStack</i> callback function queries dump stream provider on a per-thread basis.



## -prototype

````
 CALLBACK* PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK ReconstructStack;
````


## -parameters

### -param SystemThreadId [in]

A system thread ID.


### -param NativeFrames [in]

Native frames.


### -param CountNativeFrames [in]

Specifies the number of native frames.


### -param StackSymFrames [out]

A pointer to a symbol frames stack.


### -param StackSymFramesFilled [out]

Symbol frames stack filled value.


## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
This function returns stack frames and symbolic data.

New in-line frames may be provided.

Stack dump provider must be enabled.

<i>ReconstructStack</i> is called <b>PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK</b>  in the Dbgeng.h header file.</p>