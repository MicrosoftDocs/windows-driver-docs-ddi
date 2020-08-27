---
UID: NF:dbgeng.IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide
title: IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide (dbgeng.h)
description: Launches and attaches to a Process Lifecycle Management (PLM) background task.
old-location: debugger\idebugplmclient3_activateanddebugplmbgtaskwide.htm
tech.root: debugger
ms.assetid: 77358032-1777-46F4-BF16-5DFFAC15E672
ms.date: 05/03/2018
keywords: ["IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide"]
ms.keywords: ActivateAndDebugPlmBgTaskWide, ActivateAndDebugPlmBgTaskWide method [Windows Debugging], ActivateAndDebugPlmBgTaskWide method [Windows Debugging],IDebugPlmClient3 interface, IDebugPlmClient3 interface [Windows Debugging],ActivateAndDebugPlmBgTaskWide method, IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide, IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide, dbgeng/IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide, debugger.idebugplmclient3_activateanddebugplmbgtaskwide
f1_keywords:
 - "dbgeng/IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide"
 - "IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugPlmClient3.ActivateAndDebugPlmBgTaskWide
targetos: Windows
req.typenames: 
---

# IDebugPlmClient3::ActivateAndDebugPlmBgTaskWide


## -description


    Launches and attaches to a Process Lifecycle Management (PLM) background task.


## -parameters




### -param Server 
[in]
The server of the task.


### -param PackageFullName 
[in]
A pointer to the package name.


### -param BackgroundTaskId 
[in]
A pointer to the task ID. 


## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

If a debugger session is not already started, this method starts one. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient3">IDebugPlmClient3</a>
 

 

