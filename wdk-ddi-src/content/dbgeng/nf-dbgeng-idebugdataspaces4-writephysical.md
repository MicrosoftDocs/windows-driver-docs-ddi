---
UID: NF:dbgeng.IDebugDataSpaces4.WritePhysical
title: IDebugDataSpaces4::WritePhysical method
author: windows-driver-content
description: The WritePhysical method writes data to the specified physical address in the target's memory.
old-location: debugger\writephysical3.htm
old-project: debugger
ms.assetid: ec691a7c-a569-49dd-af13-bfbf403be297
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IDebugDataSpaces4, IDebugDataSpaces2::WritePhysical, IDebugDataSpaces2 interface [Windows Debugging], WritePhysical method, dbgeng/IDebugDataSpaces4::WritePhysical, WritePhysical, IDebugDataSpaces4::WritePhysical, IDebugDataSpaces3, IDebugDataSpaces, dbgeng/IDebugDataSpaces2::WritePhysical, IDebugDataSpaces_0e781d56-64f8-4518-b748-5afe9f43c429.xml, WritePhysical method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces3 interface [Windows Debugging], WritePhysical method, IDebugDataSpaces4 interface [Windows Debugging], WritePhysical method, dbgeng/IDebugDataSpaces::WritePhysical, WritePhysical method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces::WritePhysical, debugger.writephysical3, IDebugDataSpaces2, dbgeng/IDebugDataSpaces3::WritePhysical, WritePhysical method [Windows Debugging], IDebugDataSpaces4 interface, WritePhysical method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces interface [Windows Debugging], WritePhysical method, WritePhysical method [Windows Debugging], IDebugDataSpaces3::WritePhysical
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
-	Dbgeng.h
apiname:
-	IDebugDataSpaces.WritePhysical
-	IDebugDataSpaces2.WritePhysical
-	IDebugDataSpaces3.WritePhysical
-	IDebugDataSpaces4.WritePhysical
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugDataSpaces4::WritePhysical method


## -description


The <b>WritePhysical</b> method writes data to the specified physical address in the target's memory.


## -syntax


````
HRESULT WritePhysical(
  [in]            ULONG64 Offset,
  [in]            PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesWritten
);
````


## -parameters




### -param Offset [in]

Specifies the physical address of the memory to write the data to.


### -param Buffer [in]

Specifies the data to write.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes written to the target's memory.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


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
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.




## -remarks



This method is only available in kernel-mode debugging.



