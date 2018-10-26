---
UID: NF:dbgeng.IDebugSymbols3.GetImagePath
title: IDebugSymbols3::GetImagePath
author: windows-driver-content
description: The GetImagePath method returns the executable image path.
old-location: debugger\getimagepath.htm
tech.root: debugger
ms.assetid: 9310dc82-b80f-45bb-9d8a-1239330bc799
ms.date: 05/03/2018
ms.keywords: GetImagePath, GetImagePath method [Windows Debugging], GetImagePath method [Windows Debugging],IDebugSymbols interface, GetImagePath method [Windows Debugging],IDebugSymbols2 interface, GetImagePath method [Windows Debugging],IDebugSymbols3 interface, IDebugSymbols interface [Windows Debugging],GetImagePath method, IDebugSymbols2 interface [Windows Debugging],GetImagePath method, IDebugSymbols2::GetImagePath, IDebugSymbols3 interface [Windows Debugging],GetImagePath method, IDebugSymbols3.GetImagePath, IDebugSymbols3::GetImagePath, IDebugSymbols::GetImagePath, IDebugSymbols_9d38f509-e800-4090-901b-6dc78710c15f.xml, dbgeng/IDebugSymbols2::GetImagePath, dbgeng/IDebugSymbols3::GetImagePath, dbgeng/IDebugSymbols::GetImagePath, debugger.getimagepath
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
-	IDebugSymbols.GetImagePath
-	IDebugSymbols2.GetImagePath
-	IDebugSymbols3.GetImagePath
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::GetImagePath


## -description


The <b>GetImagePath</b>  method returns the executable image path.


## -parameters




### -param Buffer [out, optional]

Receives the executable image path.  This is a string that contains directories separated by semicolons (<b>;</b>).  If <i>Buffer</i> is <b>NULL</b>, this information is not returned.


### -param BufferSize [in]

Specifies the size, in characters, of the <i>Buffer</i> buffer.


### -param PathSize [out, optional]

Receives the size, in characters, of the executable image path.


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
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the executable image path and the path was truncated.

</td>
</tr>
</table>
 




## -remarks



The executable image path is used by the engine when searching for executable images.

The executable image path can consist of several directories separated by semicolons.  These directories are searched in order.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538092">AppendImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>
 

 

