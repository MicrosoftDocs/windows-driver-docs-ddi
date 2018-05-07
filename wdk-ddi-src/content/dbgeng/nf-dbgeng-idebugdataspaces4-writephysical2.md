---
UID: NF:dbgeng.IDebugDataSpaces4.WritePhysical2
title: IDebugDataSpaces4::WritePhysical2
author: windows-driver-content
description: The WritePhysical2 method writes data to the specified physical address in the target's memory.
old-location: debugger\writephysical2.htm
old-project: debugger
ms.assetid: 15a83343-b95b-4f79-b4f2-ed2ad60d170e
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: IDebugDataSpaces4 interface [Windows Debugging],WritePhysical2 method, IDebugDataSpaces4.WritePhysical2, IDebugDataSpaces4::WritePhysical2, IDebugDataSpaces_bc084790-b047-4257-b7fd-578fd4454747.xml, WritePhysical2, WritePhysical2 method [Windows Debugging], WritePhysical2 method [Windows Debugging],IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces4::WritePhysical2, debugger.writephysical2
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
-	IDebugDataSpaces4.WritePhysical2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDebugDataSpaces4::WritePhysical2


## -description


The <b>WritePhysical2</b> method writes data to the specified physical address in the target's memory.


## -parameters




### -param Offset [in]

Specifies the physical address of the memory to write the data to.


### -param Flags [in]

Specifies the properties of the physical memory to be written to.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
DEBUG_PHYSICAL_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>
 


### -param Buffer [in]

Specifies the data to write.


### -param BufferSize [in]

Specifies the size, in bytes, of the <i>Buffer</i> buffer.  This is the maximum number of bytes that will be written.


### -param BytesWritten [out, optional]

Receives the number of bytes written to the target's memory.  If <i>BytesWritten</i> is <b>NULL</b>, this information is not returned.


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

The flags DEBUG_PHYSICAL_CACHED, DEBUG_PHYSICAL_UNCACHED, and DEBUG_PHYSICAL_WRITE_COMBINED can only be used when the target is a live kernel target that is being debugged in the standard way (using a COM port, 1394 bus, or named pipe).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff550546">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561432">WritePhysical</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561441">WritePhysical2</a>
 

 

