---
UID: NF:dbgeng.IDebugSymbols3.GetOffsetByLineWide
title: IDebugSymbols3::GetOffsetByLineWide method
author: windows-driver-content
description: The GetOffsetByLineWide method returns the location of the instruction that corresponds to a specified line in the source code.
old-location: debugger\getoffsetbylinewide.htm
old-project: debugger
ms.assetid: ba09333e-84a5-4166-a859-e09c0cf74347
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetOffsetByLineWide method [Windows Debugging], GetOffsetByLineWide method [Windows Debugging], IDebugSymbols3 interface, GetOffsetByLineWide,IDebugSymbols3.GetOffsetByLineWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetOffsetByLineWide method, IDebugSymbols3::GetOffsetByLineWide, dbgeng/IDebugSymbols3::GetOffsetByLineWide, debugger.getoffsetbylinewide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
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
-	IDebugSymbols3.GetOffsetByLineWide
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::GetOffsetByLineWide method


## -description


The <b>GetOffsetByLineWide</b>  method returns the location of the instruction that corresponds to a specified line in the source code.


## -parameters




### -param Line [in]

Specifies the line number in the source file.


### -param File [in]

Specifies the file name of the source file.


### -param Offset [out]

Receives the location in the target's virtual address space of an instruction for the specified line.


## -returns



This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.

</td>
</tr>
</table>
 




## -remarks



A line in a source file might correspond to multiple instructions and this method can return any one of these instructions.

For more information about source files, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff560141">Using Source Files</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546995">GetLineByOffset</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

