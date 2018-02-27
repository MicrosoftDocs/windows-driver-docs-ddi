---
UID: NC:netdispumdddi.PFN_CREATE_MIRACAST_CONTEXT
title: PFN_CREATE_MIRACAST_CONTEXT
author: windows-driver-content
description: Called by the operating system to create a user-mode Miracast context.
old-location: display\createmiracastcontext.htm
old-project: display
ms.assetid: 3b10ddd9-a48d-4f96-b35e-db017d1f9583
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: CreateMiracastContext, CreateMiracastContext callback function [Display Devices], PFN_CREATE_MIRACAST_CONTEXT, display.createmiracastcontext, netdispumdddi/CreateMiracastContext
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
-	CreateMiracastContext
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_CREATE_MIRACAST_CONTEXT callback


## -description


Called by the operating system to create a user-mode Miracast context.


## -prototype


````
PFN_CREATE_MIRACAST_CONTEXT CreateMiracastContext;

NTSTATUS NTAPI* CreateMiracastContext(
  _In_  HANDLE             hMiracastDeviceHandle,
  _In_  MIRACAST_CALLBACKS *pMiracastCallbacks,
  _Out_ PVOID              *ppMiracastContext
)
{ ... }
````


## -parameters




### -param hMiracastDeviceHandle [in]

A handle to the current Miracast display device, supplied by the operating system.


### -param *pMiracastCallbacks [in]

A pointer to a <a href="..\netdispumdddi\ns-netdispumdddi-_miracast_callbacks.md">MIRACAST_CALLBACKS</a> structure that has pointers to callback functions, supplied by the operating system,  that the Miracast user-mode driver can call.


### -param *ppMiracastContext [out]

A pointer to a buffer, supplied by the operating system, that holds the Miracast context that the Miracast user-mode driver returns.


## -returns



On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.




## -remarks



When this function is called, the Miracast user-mode driver should prepare all resources that it needs for a new Miracast connected session.

The driver can call the callback functions pointed to by <i>pMiracastCallbacks</i> only during the lifetime of the current Miracast context.


#### Thread Safety

The operating system guarantees that only one of the <i>CreateMiracastContext</i>, <a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>, <a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>, and <a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a> functions is called at a time.




## -see-also

<a href="..\netdispumdddi\nc-netdispumdddi-pfn_start_miracast_session.md">StartMiracastSession</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_stop_miracast_session.md">StopMiracastSession</a>



<a href="..\netdispumdddi\ns-netdispumdddi-_miracast_callbacks.md">MIRACAST_CALLBACKS</a>



<a href="..\netdispumdddi\nc-netdispumdddi-pfn_destroy_miracast_context.md">DestroyMiracastContext</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFN_CREATE_MIRACAST_CONTEXT callback function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

