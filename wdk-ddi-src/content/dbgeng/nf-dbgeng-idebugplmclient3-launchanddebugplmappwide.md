---
UID: NF:dbgeng.IDebugPlmClient3.LaunchAndDebugPlmAppWide
title: IDebugPlmClient3::LaunchAndDebugPlmAppWide method
author: windows-driver-content
description: Launches and attaches to a Process Lifecycle Management (PLM) application.
old-location: debugger\idebugplmclient3_launchanddebugplmappwide.htm
old-project: debugger
ms.assetid: F3DD5912-46E5-43E5-A920-940FC8FCD83F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], LaunchAndDebugPlmAppWide method, IDebugPlmClient3::LaunchAndDebugPlmAppWide, LaunchAndDebugPlmAppWide method [Windows Debugging], LaunchAndDebugPlmAppWide method [Windows Debugging], IDebugPlmClient3 interface, LaunchAndDebugPlmAppWide,IDebugPlmClient3.LaunchAndDebugPlmAppWide, dbgeng/IDebugPlmClient3::LaunchAndDebugPlmAppWide, debugger.idebugplmclient3_launchanddebugplmappwide
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
-	IDebugPlmClient3.LaunchAndDebugPlmAppWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugPlmClient3::LaunchAndDebugPlmAppWide method


## -description


    Launches and attaches to a Process Lifecycle Management (PLM) application. 


## -syntax


````
HRESULT LaunchAndDebugPlmAppWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName,
  [in] PCWSTR  AppName,
  [in] PCWSTR  Arguments
);
````


## -parameters




### -param Server [in]

The server of the application.


### -param PackageFullName [in]

A pointer to the package name.


### -param AppName [in]

A pointer to the application name. 


### -param Arguments [in]

A pointer to an arguments string. 


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

If a debugger session is not already started, this method starts one. 




## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>



 

 


