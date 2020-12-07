---
UID: NF:dbgeng.IDebugPlmClient.LaunchPlmPackageForDebugWide
title: IDebugPlmClient::LaunchPlmPackageForDebugWide (dbgeng.h)
description: Launches a suspended Process Lifecycle Management (PLM) application.
old-location: debugger\idebugplmclient_launchplmpackagefordebugwide.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["IDebugPlmClient::LaunchPlmPackageForDebugWide"]
ms.keywords: IDebugPlmClient interface [Windows Debugging],LaunchPlmPackageForDebugWide method, IDebugPlmClient.LaunchPlmPackageForDebugWide, IDebugPlmClient::LaunchPlmPackageForDebugWide, LaunchPlmPackageForDebugWide, LaunchPlmPackageForDebugWide method [Windows Debugging], LaunchPlmPackageForDebugWide method [Windows Debugging],IDebugPlmClient interface, dbgeng/IDebugPlmClient::LaunchPlmPackageForDebugWide, debugger.idebugplmclient_launchplmpackagefordebugwide
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
 - IDebugPlmClient::LaunchPlmPackageForDebugWide
 - dbgeng/IDebugPlmClient::LaunchPlmPackageForDebugWide
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - dbgeng.h
api_name:
 - IDebugPlmClient.LaunchPlmPackageForDebugWide
---

# IDebugPlmClient::LaunchPlmPackageForDebugWide


## -description

Launches a suspended Process Lifecycle Management (PLM) application.

## -parameters

### -param Server 

[in]
The server of the application.

### -param Timeout 

[in]
A time-out value.

### -param PackageFullName 

[in]
A pointer to the package name.

### -param AppName 

[in]
A pointer to the application name.

### -param Arguments 

[in, optional]
A pointer an arguments string.

### -param ProcessId 

[out]
A pointer to a process ID output.

### -param ThreadId 

[out]
A pointer to a thread ID output.

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/dbgeng/nn-dbgeng-idebugplmclient">IDebugPlmClient</a>
