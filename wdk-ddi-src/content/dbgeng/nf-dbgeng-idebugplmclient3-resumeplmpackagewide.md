---
UID: NF:dbgeng.IDebugPlmClient3.ResumePlmPackageWide
title: IDebugPlmClient3::ResumePlmPackageWide method
author: windows-driver-content
description: Resumes a Process Lifecycle Management (PLM) package.
old-location: debugger\idebugplmclient3_resumeplmpackagewide.htm
old-project: debugger
ms.assetid: CC69357E-425B-440B-93D0-918E8586D5DF
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugPlmClient3::ResumePlmPackageWide, debugger.idebugplmclient3_resumeplmpackagewide, ResumePlmPackageWide method [Windows Debugging], IDebugPlmClient3 interface, IDebugPlmClient3 interface [Windows Debugging], ResumePlmPackageWide method, ResumePlmPackageWide, dbgeng/IDebugPlmClient3::ResumePlmPackageWide, IDebugPlmClient3, ResumePlmPackageWide method [Windows Debugging]
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
-	dbgeng.h
apiname:
-	IDebugPlmClient3.ResumePlmPackageWide
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugPlmClient3::ResumePlmPackageWide method


## -description


Resumes a Process Lifecycle Management (PLM) package.


## -syntax


````
HRESULT ResumePlmPackageWide(
  [in] ULONG64 Server,
  [in] PCWSTR  PackageFullName
);
````


## -parameters




### -param Server [in]

The server of the package.


### -param PackageFullName [in]

A pointer to the package name.


## -returns


If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



## -see-also

<a href="..\dbgeng\nn-dbgeng-idebugplmclient3.md">IDebugPlmClient3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugPlmClient3::ResumePlmPackageWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

