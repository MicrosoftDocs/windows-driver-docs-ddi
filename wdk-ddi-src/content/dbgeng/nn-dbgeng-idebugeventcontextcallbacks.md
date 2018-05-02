---
UID: NN:dbgeng.IDebugEventContextCallbacks
title: IDebugEventContextCallbacks
author: windows-driver-content
description: This interface supports event context callbacks and replaces the use of the IDebugClient::SetEventCallbacks method.
old-location: debugger\idebugeventcontextcallbacks.htm
old-project: debugger
ms.assetid: F4FAA5C9-B7D9-43B6-8B1D-CA790522900C
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugEventContextCallbacks, IDebugEventContextCallbacks interface [Windows Debugging], IDebugEventContextCallbacks interface [Windows Debugging],described, dbgeng/IDebugEventContextCallbacks, debugger.idebugeventcontextcallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugEventContextCallbacks
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugEventContextCallbacks interface


## -description


This interface supports event context callbacks and replaces the use of the <a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a> method.

Set this interface on a debugger client by using the <a href="https://msdn.microsoft.com/246573DB-5FEB-4068-8DB8-950F5EDFD1A9">IDebugClient6::SetEventContextCallbacks</a> method.


## -see-also




<a href="https://msdn.microsoft.com/246573DB-5FEB-4068-8DB8-950F5EDFD1A9">IDebugClient6::SetEventContextCallbacks</a>



<a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>
 

 

