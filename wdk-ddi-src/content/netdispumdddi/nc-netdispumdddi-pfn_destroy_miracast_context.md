---
UID: NC:netdispumdddi.PFN_DESTROY_MIRACAST_CONTEXT
title: PFN_DESTROY_MIRACAST_CONTEXT
author: windows-driver-content
description: Called by the operating system to destroy a user-mode Miracast context.
old-location: display\destroymiracastcontext.htm
tech.root: display
ms.assetid: 1b155e15-1e4e-45bb-98cc-f1c19923ed2c
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DestroyMiracastContext, DestroyMiracastContext callback function [Display Devices], PFN_DESTROY_MIRACAST_CONTEXT, PFN_DESTROY_MIRACAST_CONTEXT callback, display.destroymiracastcontext, netdispumdddi/DestroyMiracastContext
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	DestroyMiracastContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFN_DESTROY_MIRACAST_CONTEXT callback function


## -description


Called by the operating system to destroy a user-mode Miracast context.


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> function.


## -returns



Does not return a value.




## -remarks



When this function is called, the Miracast user-mode driver should release all resources it allocated when <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a> was last called.

If the display miniport driver is still reporting the Miracast monitor for this Miracast instance, the Miracast user-mode driver can optionally call the display miniport driver to immediately send a monitor departure hot-plug detection (HPD) awareness value, or it can let the display miniport driver do so in its kernel-mode <a href="https://msdn.microsoft.com/2DEEB379-C9E8-45E4-920D-D94F8C27A4EF">DxgkDdiMiracastDestroyContext</a> function.

<div class="alert"><b>Important</b>  The Miracast user-mode driver should complete this function call in 3 seconds so it does not block system plug and play (PnP) or power operations.</div>
<div> </div>
After this call completes, the operating system unloads the Miracast user-mode driver such that the driver leaves no resources still opened and no thread still running.


#### Thread Safety

The operating system guarantees that only one of the <a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>, <i>DestroyMiracastContext</i>, <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions is called at a time.




## -see-also




<a href="https://msdn.microsoft.com/3b10ddd9-a48d-4f96-b35e-db017d1f9583">CreateMiracastContext</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

