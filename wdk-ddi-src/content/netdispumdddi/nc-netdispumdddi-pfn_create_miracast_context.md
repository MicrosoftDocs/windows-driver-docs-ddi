---
UID: NC:netdispumdddi.PFN_CREATE_MIRACAST_CONTEXT
title: PFN_CREATE_MIRACAST_CONTEXT
author: windows-driver-content
description: Called by the operating system to create a user-mode Miracast context.
old-location: display\createmiracastcontext.htm
old-project: display
ms.assetid: 3b10ddd9-a48d-4f96-b35e-db017d1f9583
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Netdispumdddi.h
api_name:
-	CreateMiracastContext
product: Windows
targetos: Windows
req.typenames: NDK_SRQ_DISPATCH
---

# PFN_CREATE_MIRACAST_CONTEXT callback


## -description


Called by the operating system to create a user-mode Miracast context.


## -parameters




### -param hMiracastDeviceHandle [in]

A handle to the current Miracast display device, supplied by the operating system.


### -param *pMiracastCallbacks [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265470">MIRACAST_CALLBACKS</a> structure that has pointers to callback functions, supplied by the operating system,  that the Miracast user-mode driver can call.


### -param *ppMiracastContext [out]

A pointer to a buffer, supplied by the operating system, that holds the Miracast context that the Miracast user-mode driver returns.


## -returns



On success, this function returns <b>STATUS_SUCCESS</b>. Otherwise, the function returns an error code defined in the Ntstatus.h header.




## -remarks



When this function is called, the Miracast user-mode driver should prepare all resources that it needs for a new Miracast connected session.

The driver can call the callback functions pointed to by <i>pMiracastCallbacks</i> only during the lifetime of the current Miracast context.


#### Thread Safety

The operating system guarantees that only one of the <i>CreateMiracastContext</i>, <a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>, <a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>, and <a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a> functions is called at a time.




## -see-also




<a href="https://msdn.microsoft.com/1b155e15-1e4e-45bb-98cc-f1c19923ed2c">DestroyMiracastContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265470">MIRACAST_CALLBACKS</a>



<a href="https://msdn.microsoft.com/2778d9d0-7f97-416f-a5ae-3754b17e8a29">StartMiracastSession</a>



<a href="https://msdn.microsoft.com/ab9ad8ee-9390-41a4-9a69-2e98579b2b77">StopMiracastSession</a>
 

 

