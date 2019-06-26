---
UID: NF:dbgeng.IDebugPlmClient.LaunchPlmPackageForDebugWide
title: IDebugPlmClient::LaunchPlmPackageForDebugWide (dbgeng.h)
description: Launches a suspended Process Lifecycle Management (PLM) application.
old-location: debugger\idebugplmclient_launchplmpackagefordebugwide.htm
tech.root: debugger
ms.assetid: DE11B4A5-5AE3-4369-AF6D-6CE34B9AAFAB
ms.date: 05/03/2018
ms.keywords: IDebugPlmClient interface [Windows Debugging],LaunchPlmPackageForDebugWide method, IDebugPlmClient.LaunchPlmPackageForDebugWide, IDebugPlmClient::LaunchPlmPackageForDebugWide, LaunchPlmPackageForDebugWide, LaunchPlmPackageForDebugWide method [Windows Debugging], LaunchPlmPackageForDebugWide method [Windows Debugging],IDebugPlmClient interface, dbgeng/IDebugPlmClient::LaunchPlmPackageForDebugWide, debugger.idebugplmclient_launchplmpackagefordebugwide
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- dbgeng.h
api_name:
- IDebugPlmClient.LaunchPlmPackageForDebugWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugPlmClient::LaunchPlmPackageForDebugWide


## -description


Launches a suspended Process Lifecycle Management (PLM) application.


## -parameters




### -param Server [in]

The server of the application.


### -param Timeout [in]

A time-out value.


### -param PackageFullName [in]

A pointer to the package name.


### -param AppName [in]

A pointer to the application name. 


### -param Arguments [in, optional]

A pointer an arguments string.


### -param ProcessId [out]

A pointer to a process ID output.


### -param ThreadId [out]

A pointer to a thread ID output.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugplmclient">IDebugPlmClient</a>
 

 

