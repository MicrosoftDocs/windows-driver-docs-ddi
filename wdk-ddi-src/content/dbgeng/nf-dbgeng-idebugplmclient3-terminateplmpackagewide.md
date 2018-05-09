---
UID: NF:dbgeng.IDebugPlmClient3.TerminatePlmPackageWide
title: IDebugPlmClient3::TerminatePlmPackageWide
author: windows-driver-content
description: Ends a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_terminateplmpackagewide.htm
old-project: debugger
ms.assetid: EBEEF2C7-AD2E-4BE5-B20C-D4E148F1454C
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugPlmClient3 interface [Windows Debugging],TerminatePlmPackageWide method, IDebugPlmClient3.TerminatePlmPackageWide, IDebugPlmClient3::TerminatePlmPackageWide, TerminatePlmPackageWide, TerminatePlmPackageWide method [Windows Debugging], TerminatePlmPackageWide method [Windows Debugging],IDebugPlmClient3 interface, dbgeng/IDebugPlmClient3::TerminatePlmPackageWide, debugger.idebugplmclient3_terminateplmpackagewide
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
-	IDebugPlmClient3.TerminatePlmPackageWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugPlmClient3::TerminatePlmPackageWide


## -description


Ends a Process Lifecycle Management (PLM) package.


## -parameters




### -param Server [in]

The server of the package.


### -param PackageFullName [in]

A pointer to the package name.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/5B0580FF-0829-406A-B511-C0CD91A08D5F">IDebugPlmClient3</a>
 

 

