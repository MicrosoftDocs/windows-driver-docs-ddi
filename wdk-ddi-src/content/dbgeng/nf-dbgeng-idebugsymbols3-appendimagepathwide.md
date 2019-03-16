---
UID: NF:dbgeng.IDebugSymbols3.AppendImagePathWide
title: IDebugSymbols3::AppendImagePathWide (dbgeng.h)
description: The AppendImagePathWide method appends directories to the executable image path.
old-location: debugger\appendimagepathwide.htm
tech.root: debugger
ms.assetid: 9a129ce5-4493-4838-9a6c-8a3c054e7c27
ms.date: 05/03/2018
ms.keywords: AppendImagePathWide, AppendImagePathWide method [Windows Debugging], AppendImagePathWide method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols3 interface [Windows Debugging],AppendImagePathWide method, IDebugSymbols3.AppendImagePathWide, IDebugSymbols3::AppendImagePathWide, dbgeng/IDebugSymbols3::AppendImagePathWide, debugger.appendimagepathwide
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Dbgeng.h
api_name:
- IDebugSymbols3.AppendImagePathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::AppendImagePathWide


## -description


The <b>AppendImagePathWide</b>  method appends directories to the executable image path.


## -parameters




### -param Addition [in]

Specifies the directories to append to the executable image path.  This is a string that contains directory names separated by semicolons (;).


## -returns



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
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



The executable image path is used by the <a href="https://msdn.microsoft.com/1e32bd40-8c77-4c6b-913c-6ec26707ed36">engine</a> when searching for executable images.

The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>
 

 

