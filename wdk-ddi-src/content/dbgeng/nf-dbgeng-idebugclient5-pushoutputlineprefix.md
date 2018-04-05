---
UID: NF:dbgeng.IDebugClient5.PushOutputLinePrefix
title: IDebugClient5::PushOutputLinePrefix method
author: windows-driver-content
description: Saves an output line prefix.
old-location: debugger\idebugclient5_pushoutputlineprefix.htm
old-project: debugger
ms.assetid: 20446E2D-94D3-43D6-ABBF-2FA15F089659
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: IDebugClient5, IDebugClient5 interface [Windows Debugging], PushOutputLinePrefix method, IDebugClient5::PushOutputLinePrefix, PushOutputLinePrefix method [Windows Debugging], PushOutputLinePrefix method [Windows Debugging], IDebugClient5 interface, PushOutputLinePrefix,IDebugClient5.PushOutputLinePrefix, dbgeng/IDebugClient5::PushOutputLinePrefix, debugger.idebugclient5_pushoutputlineprefix
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
-	IDebugClient5.PushOutputLinePrefix
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugClient5::PushOutputLinePrefix method


## -description


    Saves an output line prefix.


## -parameters




### -param NewPrefix [in, optional]

A pointer to the new output line prefix.


### -param Handle [out]

The handle of the previous output line prefix.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

