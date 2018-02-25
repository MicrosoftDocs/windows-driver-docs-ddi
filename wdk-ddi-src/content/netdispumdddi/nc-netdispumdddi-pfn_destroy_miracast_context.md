---
UID: NC:netdispumdddi.PFN_DESTROY_MIRACAST_CONTEXT
title: PFN_DESTROY_MIRACAST_CONTEXT
author: windows-driver-content
description: Called by the operating system to destroy a user-mode Miracast context.
old-location: display\destroymiracastcontext.htm
old-project: display
ms.assetid: 1b155e15-1e4e-45bb-98cc-f1c19923ed2c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: DestroyMiracastContext, DestroyMiracastContext callback function [Display Devices], PFN_DESTROY_MIRACAST_CONTEXT, display.destroymiracastcontext, netdispumdddi/DestroyMiracastContext
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Netdispumdddi.h
apiname:
-	DestroyMiracastContext
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_DESTROY_MIRACAST_CONTEXT callback


## -description


Called by the operating system to destroy a user-mode Miracast context.


## -prototype


````
PFN_DESTROY_MIRACAST_CONTEXT DestroyMiracastContext;

VOID NTAPI* DestroyMiracastContext(
  _In_ PVOID pMiracastContext
)
{ ... }
````


## -parameters




### -param pMiracastContext [in]

A pointer to a context associated with a display adapter.

The operating system obtained the context when it called the Miracast user-mode driver's <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> function.


## -returns



Does not return a value.




## -remarks



When this function is called, the Miracast user-mode driver should release all resources it allocated when <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a> was last called.

If the display miniport driver is still reporting the Miracast monitor for this Miracast instance, the Miracast user-mode driver can optionally call the display miniport driver to immediately send a monitor departure hot-plug detection (HPD) awareness value, or it can let the display miniport driver do so in its kernel-mode <a href="..\dispmprt\nc-dispmprt-dxgkddi_miracast_destroy_context.md">DxgkDdiMiracastDestroyContext</a> function.

<div class="alert"><b>Important</b>  The Miracast user-mode driver should complete this function call in 3 seconds so it does not block system plug and play (PnP) or power operations.</div>
<div> </div>
After this call completes, the operating system unloads the Miracast user-mode driver such that the driver leaves no resources still opened and no thread still running.


#### Thread Safety

The operating system guarantees that only one of the <a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>, <i>DestroyMiracastContext</i>, <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>, and <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> functions is called at a time.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_create_miracast_context.md">CreateMiracastContext</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_DESTROY_MIRACAST_CONTEXT callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

