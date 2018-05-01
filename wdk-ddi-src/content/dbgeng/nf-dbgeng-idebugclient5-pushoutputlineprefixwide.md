---
UID: NF:dbgeng.IDebugClient5.PushOutputLinePrefixWide
title: IDebugClient5::PushOutputLinePrefixWide
author: windows-driver-content
description: Saves a wide string output line prefix.
old-location: debugger\idebugclient5_pushoutputlineprefixwide.htm
old-project: debugger
ms.assetid: B3D4AE97-9CDB-425D-A04B-E164852FDF19
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugClient5 interface [Windows Debugging],PushOutputLinePrefixWide method, IDebugClient5.PushOutputLinePrefixWide, IDebugClient5::PushOutputLinePrefixWide, PushOutputLinePrefixWide, PushOutputLinePrefixWide method [Windows Debugging], PushOutputLinePrefixWide method [Windows Debugging],IDebugClient5 interface, dbgeng/IDebugClient5::PushOutputLinePrefixWide, debugger.idebugclient5_pushoutputlineprefixwide
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
-	IDebugClient5.PushOutputLinePrefixWide
product: Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::PushOutputLinePrefixWide


## -description


    Saves a wide string output line prefix.


## -parameters




### -param NewPrefix [in, optional]

A pointer to the new output line Unicode character prefix.


### -param Handle [out]

The handle of the previous output line prefix.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

