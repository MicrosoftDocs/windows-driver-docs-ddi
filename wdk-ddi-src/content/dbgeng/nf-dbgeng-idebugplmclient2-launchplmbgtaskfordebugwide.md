---
UID: NF:dbgeng.IDebugPlmClient2.LaunchPlmBgTaskForDebugWide
title: IDebugPlmClient2::LaunchPlmBgTaskForDebugWide (dbgeng.h)
description: Launches a suspended Process Lifecycle Management (PLM) background task.
old-location: debugger\idebugplmclient2_launchplmbgtaskfordebugwide.htm
tech.root: debugger
ms.assetid: 47793815-F7AC-4E0D-809C-DBB7497BDA30
ms.date: 05/03/2018
keywords: ["IDebugPlmClient2::LaunchPlmBgTaskForDebugWide"]
ms.keywords: IDebugPlmClient2 interface [Windows Debugging],LaunchPlmBgTaskForDebugWide method, IDebugPlmClient2.LaunchPlmBgTaskForDebugWide, IDebugPlmClient2::LaunchPlmBgTaskForDebugWide, LaunchPlmBgTaskForDebugWide, LaunchPlmBgTaskForDebugWide method [Windows Debugging], LaunchPlmBgTaskForDebugWide method [Windows Debugging],IDebugPlmClient2 interface, dbgeng/IDebugPlmClient2::LaunchPlmBgTaskForDebugWide, debugger.idebugplmclient2_launchplmbgtaskfordebugwide
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDebugPlmClient2::LaunchPlmBgTaskForDebugWide
 - dbgeng/IDebugPlmClient2::LaunchPlmBgTaskForDebugWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient2.LaunchPlmBgTaskForDebugWide
---

# IDebugPlmClient2::LaunchPlmBgTaskForDebugWide


## -description

Launches a suspended Process Lifecycle Management (PLM) background task.

## -parameters

### -param Server 

[in]
The server of the task.

### -param Timeout 

[in]
A time-out value.

### -param PackageFullName 

[in]
A pointer to the package name.

### -param BackgroundTaskId 

[in]
A pointer to the task ID.

### -param ProcessId 

[out]
A pointer to a process ID output.

### -param ThreadId 

[out]
A pointer to a thread ID output.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient2">IDebugPlmClient2</a>