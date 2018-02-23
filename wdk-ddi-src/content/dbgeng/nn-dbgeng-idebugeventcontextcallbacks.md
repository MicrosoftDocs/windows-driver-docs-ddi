---
UID: NN:dbgeng.IDebugEventContextCallbacks
title: IDebugEventContextCallbacks
author: windows-driver-content
description: This interface supports event context callbacks and replaces the use of the IDebugClient::SetEventCallbacks method.
old-location: debugger\idebugeventcontextcallbacks.htm
old-project: Debugger
ms.assetid: F4FAA5C9-B7D9-43B6-8B1D-CA790522900C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.idebugeventcontextcallbacks, IDebugEventContextCallbacks interface [Windows Debugging], IDebugEventContextCallbacks interface [Windows Debugging], described, IDebugEventContextCallbacks, dbgeng/IDebugEventContextCallbacks
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugEventContextCallbacks
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugEventContextCallbacks interface


## -description


This interface supports event context callbacks and replaces the use of the <a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a> method.

Set this interface on a debugger client by using the <a href="https://msdn.microsoft.com/246573DB-5FEB-4068-8DB8-950F5EDFD1A9">IDebugClient6::SetEventContextCallbacks</a> method.


## -see-also

<a href="https://msdn.microsoft.com/246573DB-5FEB-4068-8DB8-950F5EDFD1A9">IDebugClient6::SetEventContextCallbacks</a>



<a href="https://msdn.microsoft.com/c741777b-dfaf-42b0-9dd7-6678281b6359">IDebugClient::SetEventCallbacks</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugEventContextCallbacks interface%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

