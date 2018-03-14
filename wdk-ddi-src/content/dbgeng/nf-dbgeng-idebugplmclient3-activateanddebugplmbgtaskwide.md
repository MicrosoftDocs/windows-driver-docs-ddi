---
UID: NF:dbgeng.IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide
title: IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide method
author: windows-driver-content
description: Launches and attaches to a Process Lifecycle Management (PLM) background task.
old-location: debugger\idebugplmclient3_activateanddebugplmbgtaskwide.htm
old-project: debugger
ms.assetid: 77358032-1777-46F4-BF16-5DFFAC15E672
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ActivateAndDebugPlmBgTaskWide method [Windows Debugging], ActivateAndDebugPlmBgTaskWide method [Windows Debugging], IDebugPlmClient3 interface, ActivateAndDebugPlmBgTaskWide,IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide, IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], ActivateAndDebugPlmBgTaskWide method, IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide, dbgeng/IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide, debugger.idebugplmclient3_activateanddebugplmbgtaskwide
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
-	IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide method


## -description


    Launches and attaches to a Process Lifecycle Management (PLM) background task.


## -syntax


````
HRESULT ActivateAndDebugPlmBgTaskWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName,
  [in] PCWSTR  BackgroundTaskId
);
````


## -parameters




### -param Server [in]

The server of the task.


### -param PackageFullName [in]

A pointer to the package name.


### -param BackgroundTaskId [in]

A pointer to the task ID. 


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

If a debugger session is not already started, this method starts one. 




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>



 

 


