---
UID: NF:dbgeng.IDebugOutputStream.Write
title: IDebugOutputStream::Write (dbgeng.h)
description: Writes to the debug output stream.
old-location: debugger\idebugoutputstream_write.htm
tech.root: debugger
ms.assetid: CC609DA8-9778-4AFC-9205-5F68AF15927C
ms.date: 05/03/2018
ms.keywords: IDebugOutputStream interface [Windows Debugging],Write method, IDebugOutputStream.Write, IDebugOutputStream::Write, Write, Write method [Windows Debugging], Write method [Windows Debugging],IDebugOutputStream interface, dbgeng/IDebugOutputStream::Write, debugger.idebugoutputstream_write
ms.topic: method
f1_keywords:
 - "dbgeng/IDebugOutputStream.Write"
req.header: dbgeng.h
req.include-header: 
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
- IDebugOutputStream.Write
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugOutputStream::Write


## -description


Writes to the debug output stream.


## -parameters




### -param psz [in]

A pointer to a Unicode character string of content to write.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/dbgeng/nn-dbgeng-idebugoutputstream">IDebugOutputStream</a>
 

 

