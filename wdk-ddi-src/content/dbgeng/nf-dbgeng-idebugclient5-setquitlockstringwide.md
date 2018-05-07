---
UID: NF:dbgeng.IDebugClient5.SetQuitLockStringWide
title: IDebugClient5::SetQuitLockStringWide
author: windows-driver-content
description: Sets a quit lock Unicode character string.
old-location: debugger\idebugclient5_setquitlockstringwide.htm
old-project: debugger
ms.assetid: B9A2C636-BF18-4D1B-A013-8CAE65FCC56F
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],SetQuitLockStringWide method, IDebugClient5.SetQuitLockStringWide, IDebugClient5::SetQuitLockStringWide, SetQuitLockStringWide, SetQuitLockStringWide method [Windows Debugging], SetQuitLockStringWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::SetQuitLockStringWide, debugger.idebugclient5_setquitlockstringwide
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
-	IDebugClient5.SetQuitLockStringWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::SetQuitLockStringWide


## -description


Sets a quit lock Unicode character string. 


## -parameters




### -param String [in]

A pointer to the quit lock Unicode character string.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



    This function provides control over locking the session against
    undesired quits.  




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

