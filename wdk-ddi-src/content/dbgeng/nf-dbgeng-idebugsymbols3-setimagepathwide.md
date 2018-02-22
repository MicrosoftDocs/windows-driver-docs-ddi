---
UID: NF:dbgeng.IDebugSymbols3.SetImagePathWide
title: IDebugSymbols3::SetImagePathWide method
author: windows-driver-content
description: The SetImagePathWide method sets the executable image path.
old-location: debugger\setimagepathwide.htm
old-project: Debugger
ms.assetid: 0675dce8-4724-4880-b311-204fbb6fe194
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.setimagepathwide, IDebugSymbols3::SetImagePathWide, IDebugSymbols3 interface [Windows Debugging], SetImagePathWide method, IDebugSymbols3, SetImagePathWide method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols3::SetImagePathWide, SetImagePathWide method [Windows Debugging], SetImagePathWide
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols3.SetImagePathWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols3::SetImagePathWide method


## -description


The <b>SetImagePathWide</b>  method sets the executable image path.


## -syntax


````
HRESULT SetImagePathWide(
  [in] PCWSTR Path
);
````


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



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols3::SetImagePathWide method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

