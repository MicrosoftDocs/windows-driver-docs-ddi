---
UID: NC:netdispumdddi.PFN_DESTROY_MIRACAST_CONTEXT
title: PFN_DESTROY_MIRACAST_CONTEXT (netdispumdddi.h)
description: Called by the operating system to destroy a user-mode Miracast context.
old-location: display\destroymiracastcontext.htm
tech.root: display
ms.assetid: 1b155e15-1e4e-45bb-98cc-f1c19923ed2c
ms.date: 05/10/2018
ms.keywords: DestroyMiracastContext, DestroyMiracastContext callback function [Display Devices], PFN_DESTROY_MIRACAST_CONTEXT, PFN_DESTROY_MIRACAST_CONTEXT callback, display.destroymiracastcontext, netdispumdddi/DestroyMiracastContext
ms.topic: callback
f1_keywords:
 - "netdispumdddi/DestroyMiracastContext"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Netdispumdddi.h
api_name:
- DestroyMiracastContext
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

The operating system obtained the context when it called the Miracast user-mode driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> function.


## -returns



Does not return a value.




## -remarks



When this function is called, the Miracast user-mode driver should release all resources it allocated when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a> was last called.

If the display miniport driver is still reporting the Miracast monitor for this Miracast instance, the Miracast user-mode driver can optionally call the display miniport driver to immediately send a monitor departure hot-plug detection (HPD) awareness value, or it can let the display miniport driver do so in its kernel-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_miracast_destroy_context">DxgkDdiMiracastDestroyContext</a> function.

<div class="alert"><b>Important</b>  The Miracast user-mode driver should complete this function call in 3 seconds so it does not block system plug and play (PnP) or power operations.</div>
<div> </div>
After this call completes, the operating system unloads the Miracast user-mode driver such that the driver leaves no resources still opened and no thread still running.


#### Thread Safety

The operating system guarantees that only one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>, <i>DestroyMiracastContext</i>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a> functions is called at a time.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_create_miracast_context">CreateMiracastContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_start_miracast_session">StartMiracastSession</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/netdispumdddi/nc-netdispumdddi-pfn_stop_miracast_session">StopMiracastSession</a>
 

 

