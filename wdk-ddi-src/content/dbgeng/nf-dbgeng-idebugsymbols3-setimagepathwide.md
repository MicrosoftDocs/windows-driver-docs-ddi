---
UID: NF:dbgeng.IDebugSymbols3.SetImagePathWide
title: IDebugSymbols3::SetImagePathWide (dbgeng.h)
description: The SetImagePathWide method sets the executable image path.
old-location: debugger\setimagepathwide.htm
tech.root: debugger
ms.assetid: 0675dce8-4724-4880-b311-204fbb6fe194
ms.date: 05/03/2018
ms.keywords: IDebugSymbols3 interface [Windows Debugging],SetImagePathWide method, IDebugSymbols3.SetImagePathWide, IDebugSymbols3::SetImagePathWide, SetImagePathWide, SetImagePathWide method [Windows Debugging], SetImagePathWide method [Windows Debugging],IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetImagePathWide, debugger.setimagepathwide
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
-	IDebugSymbols3.SetImagePathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugSymbols3::SetImagePathWide


## -description


The <b>SetImagePathWide</b>  method sets the executable image path.


## -parameters




### -param Path [in]

Specifies the new executable image path.  This is a string that contains directories separated by semicolons (;).


## -returns



This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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



The executable image path is used by the engine when searching for executable images.

The executable image path can consist of several directories separated by semicolons.  These directories are searched in order.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff538092">AppendImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>
 

 

