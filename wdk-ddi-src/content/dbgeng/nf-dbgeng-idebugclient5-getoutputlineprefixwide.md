---
UID: NF:dbgeng.IDebugClient5.GetOutputLinePrefixWide
title: IDebugClient5::GetOutputLinePrefixWide
author: windows-driver-content
description: Gets a Unicode character string prefix for output lines.
old-location: debugger\idebugclient5_getoutputlineprefixwide.htm
old-project: debugger
ms.assetid: 145A478E-826B-4E82-B358-6140D3A4063F
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: GetOutputLinePrefixWide, GetOutputLinePrefixWide method [Windows Debugging], GetOutputLinePrefixWide method [Windows Debugging],IDebugClient5 interface, IDebugClient5 interface [Windows Debugging],GetOutputLinePrefixWide method, IDebugClient5.GetOutputLinePrefixWide, IDebugClient5::GetOutputLinePrefixWide, dbgeng/IDebugClient5::GetOutputLinePrefixWide, debugger.idebugclient5_getoutputlineprefixwide
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
-	IDebugClient5.GetOutputLinePrefixWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugClient5::GetOutputLinePrefixWide


## -description


Gets a Unicode character string prefix for output lines.


## -parameters




### -param Buffer [out]

The pointer to the buffer of the prefix.


### -param BufferSize [in]

The length of the buffer.


### -param PrefixSize [out, optional]

A pointer to the length of the prefix.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550497">IDebugClient5</a>
 

 

