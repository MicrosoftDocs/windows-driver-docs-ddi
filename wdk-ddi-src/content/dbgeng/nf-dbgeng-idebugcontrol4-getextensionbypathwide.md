---
UID: NF:dbgeng.IDebugControl4.GetExtensionByPathWide
title: IDebugControl4::GetExtensionByPathWide (dbgeng.h)
description: The GetExtensionByPathWide method returns the handle for an already loaded extension library.
old-location: debugger\getextensionbypathwide.htm
tech.root: debugger
ms.assetid: 85257190-2b39-487d-ada6-4c8cd0b1450f
ms.date: 05/03/2018
ms.keywords: GetExtensionByPathWide, GetExtensionByPathWide method [Windows Debugging], GetExtensionByPathWide method [Windows Debugging],IDebugControl4 interface, IDebugControl4 interface [Windows Debugging],GetExtensionByPathWide method, IDebugControl4.GetExtensionByPathWide, IDebugControl4::GetExtensionByPathWide, dbgeng/IDebugControl4::GetExtensionByPathWide, debugger.getextensionbypathwide
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
- dbgeng.h
api_name:
- IDebugControl4.GetExtensionByPathWide
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugControl4::GetExtensionByPathWide


## -description


The <b>GetExtensionByPathWide</b>  method returns the handle for an already loaded extension library.


## -parameters




### -param Path [in]

Specifies the fully qualified path and file name of the extension library.


### -param Handle [out]

Receives the handle of the extension library.


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



Extension libraries are loaded into the <a href="https://msdn.microsoft.com/1cc2c055-447c-44cd-94d4-ae3dfa8243fb">host engine</a>, which is where this method looks for the requested extension library.  <i>Path</i> is a path and file name for the host engine.

For more information on using extension libraries, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539033">Calling Extensions and Extension Functions</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537892">AddExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550526">IDebugControl4</a>
 

 

