---
UID: NF:dbgeng.IDebugDataSpaces4.ReadPhysical
title: IDebugDataSpaces4::ReadPhysical method
author: windows-driver-content
description: The ReadPhysical method reads the target's memory from the specified physical address.
old-location: debugger\readphysical3.htm
old-project: debugger
ms.assetid: 8df51985-9208-46ce-8802-6bc5ec707ab2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces4::ReadPhysical, ReadPhysical, IDebugDataSpaces3 interface [Windows Debugging], ReadPhysical method, IDebugDataSpaces4 interface [Windows Debugging], ReadPhysical method, dbgeng/IDebugDataSpaces4::ReadPhysical, dbgeng/IDebugDataSpaces2::ReadPhysical, IDebugDataSpaces::ReadPhysical, IDebugDataSpaces4, IDebugDataSpaces_5be1f680-1177-4cdf-a4d8-5868644a51af.xml, ReadPhysical method [Windows Debugging], IDebugDataSpaces interface, dbgeng/IDebugDataSpaces::ReadPhysical, IDebugDataSpaces2::ReadPhysical, dbgeng/IDebugDataSpaces3::ReadPhysical, IDebugDataSpaces3::ReadPhysical, ReadPhysical method [Windows Debugging], IDebugDataSpaces2 interface, IDebugDataSpaces interface [Windows Debugging], ReadPhysical method, ReadPhysical method [Windows Debugging], debugger.readphysical3, ReadPhysical method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces2 interface [Windows Debugging], ReadPhysical method, ReadPhysical method [Windows Debugging], IDebugDataSpaces4 interface
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
-	IDebugDataSpaces.ReadPhysical
-	IDebugDataSpaces2.ReadPhysical
-	IDebugDataSpaces3.ReadPhysical
-	IDebugDataSpaces4.ReadPhysical
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_GETENCRYPTIONBLTKEY
---

# IDebugDataSpaces4::ReadPhysical method


## -description


The <b>ReadPhysical</b> method reads the target's memory from the specified physical address.


## -syntax


````
HRESULT ReadPhysical(
  [in]            ULONG64 Offset,
  [out]           PVOID   Buffer,
  [in]            ULONG   BufferSize,
  [out, optional] PULONG  BytesRead
);
````


## -parameters




### -param Offset [in]

Specifies the physical address of the memory to read.


### -param Buffer [out]

Receives the memory that is read.


### -param BufferSize [in]

Specifies the size in bytes of the buffer <i>Buffer</i>.  This is the maximum number of bytes that will be read.


### -param BytesRead [out, optional]

Receives the number of bytes read from the target's memory.  If <i>BytesRead</i> is <b>NULL</b>, this information is not returned.


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


