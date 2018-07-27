---
UID: NF:dbgeng.IDebugDataSpaces.WriteControl
title: IDebugDataSpaces::WriteControl
author: windows-driver-content
description: The WriteControl method writes implementation-specific system data.
old-location: debugger\writecontrol.htm
tech.root: debugger
ms.assetid: 0b512c66-7cd8-4605-87d5-13b78d790c8c
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: IDebugDataSpaces interface [Windows Debugging],WriteControl method, IDebugDataSpaces.WriteControl, IDebugDataSpaces2 interface [Windows Debugging],WriteControl method, IDebugDataSpaces2::WriteControl, IDebugDataSpaces3 interface [Windows Debugging],WriteControl method, IDebugDataSpaces3::WriteControl, IDebugDataSpaces4 interface [Windows Debugging],WriteControl method, IDebugDataSpaces4::WriteControl, IDebugDataSpaces::WriteControl, IDebugDataSpaces_7da7d848-6188-4325-8da5-3fa3df3c68b9.xml, WriteControl, WriteControl method [Windows Debugging], WriteControl method [Windows Debugging],IDebugDataSpaces interface, WriteControl method [Windows Debugging],IDebugDataSpaces2 interface, WriteControl method [Windows Debugging],IDebugDataSpaces3 interface, WriteControl method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces2::WriteControl, dbgeng/IDebugDataSpaces3::WriteControl, dbgeng/IDebugDataSpaces4::WriteControl, dbgeng/IDebugDataSpaces::WriteControl, debugger.writecontrol
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
-	IDebugDataSpaces.WriteControl
-	IDebugDataSpaces2.WriteControl
-	IDebugDataSpaces3.WriteControl
-	IDebugDataSpaces4.WriteControl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces::WriteControl


## -description


The <b>WriteControl</b> method writes implementation-specific system data.


## -parameters




### -param Processor [in]

Specifies the processor whose information is to be written.


### -param Offset [in]

Specifies the offset of the control space of the memory to write.


### -param Buffer [in]

Specifies the data to write to the control-space memory.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes returned in the buffer <i>Buffer</i>.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


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



This method is only available in kernel-mode debugging.



