---
UID: NF:dbgeng.IDebugSymbols3.IsManagedModule
title: IDebugSymbols3::IsManagedModule method
author: windows-driver-content
description: Checks whether the engine is using managed debugging support when it retrieves information for a module.
old-location: debugger\idebugsymbols3_ismanagedmodule.htm
old-project: debugger
ms.assetid: AECBA6E8-B030-4418-A561-9E48B4880D15
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSymbols3::IsManagedModule, IsManagedModule, IsManagedModule method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging], IsManagedModule method, IDebugSymbols3::IsManagedModule, IDebugSymbols3, debugger.idebugsymbols3_ismanagedmodule, IsManagedModule method [Windows Debugging]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
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
-	Dbgeng.h
apiname: 
-	IDebugSymbols3.IsManagedModule
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::IsManagedModule method


## -description


Checks whether the engine is using managed
    debugging support when it retrieves information
    for a module.


## -syntax


````
HRESULT IsManagedModule(
  [in] ULONG   Index,
  [in] ULONG64 Base
);
````


## -parameters




### -param Index [in]

The index of a module.


### -param Base [in]

The base of the module.


## -returns


<b>IDebugSymbols3::IsManagedModule</b> returns a value of <b>S_OK</b> if the engine is using managed
    debugging support when it retrieves information
    for a module.



## -remarks


It can be expensive to run this check.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::IsManagedModule method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

