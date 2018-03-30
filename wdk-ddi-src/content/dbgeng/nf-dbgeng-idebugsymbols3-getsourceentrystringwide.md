---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryStringWide
title: IDebugSymbols3::GetSourceEntryStringWide method
author: windows-driver-content
description: Queries symbol information and returns locations in the target's memory.
old-location: debugger\idebugsymbols3_getsourceentrystringwide.htm
old-project: debugger
ms.assetid: CDB72C6A-43E5-463B-97E5-44D22214C071
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetSourceEntryStringWide method [Windows Debugging], GetSourceEntryStringWide method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryStringWide,IDebugSymbols3.GetSourceEntryStringWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryStringWide method, IDebugSymbols3::GetSourceEntryStringWide, dbgeng/IDebugSymbols3::GetSourceEntryStringWide, debugger.idebugsymbols3_getsourceentrystringwide
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
-	Dbgeng.h
api_name:
-	IDebugSymbols3.GetSourceEntryStringWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetSourceEntryStringWide method


## -description


Queries symbol information and returns locations in the target's memory.


## -parameters




### -param Entry [in]

An entry as a <a href="https://msdn.microsoft.com/library/windows/hardware/ff541680">DEBUG_SYMBOL_SOURCE_ENTRY</a> structure. 


### -param Which [in]

A value that determines which types to return.


### -param Buffer [out]

 A pointer to a Unicode character string buffer for the results.


### -param BufferSize [in]

The size of the buffer.


### -param StringSize [out, optional]

Pointer to the size of the string. 


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

    This method can return multiple results for a source lookup. This allows for all possible results to be returned.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntryStringWide method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
