---
UID: NF:dbgeng.IDebugPlmClient3.SuspendPlmPackageWide
title: IDebugPlmClient3::SuspendPlmPackageWide method
author: windows-driver-content
description: Suspends a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_suspendplmpackagewide.htm
old-project: debugger
ms.assetid: B887CCD2-0747-483E-A4CF-632471AB19A2
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugPlmClient3, IDebugPlmClient3 interface [Windows Debugging], SuspendPlmPackageWide method, IDebugPlmClient3::SuspendPlmPackageWide, SuspendPlmPackageWide method [Windows Debugging], SuspendPlmPackageWide method [Windows Debugging], IDebugPlmClient3 interface, SuspendPlmPackageWide,IDebugPlmClient3.SuspendPlmPackageWide, dbgeng/IDebugPlmClient3::SuspendPlmPackageWide, debugger.idebugplmclient3_suspendplmpackagewide
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
-	IDebugPlmClient3.SuspendPlmPackageWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugPlmClient3::SuspendPlmPackageWide method


## -description


Suspends a Process Lifecycle Management (PLM) package.


## -parameters




### -param Server [in]

The server of the package.


### -param PackageFullName [in]

A pointer to the package name.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/5B0580FF-0829-406A-B511-C0CD91A08D5F">IDebugPlmClient3</a>
 

 

