---
UID: NF:wdbgexts.ReadPhysicalWithFlags
title: ReadPhysicalWithFlags function
author: windows-driver-content
description: The ReadPhysicalWithFlags function reads from physical memory.
old-location: debugger\readphysicalwithflags.htm
tech.root: debugger
ms.assetid: 7ff5787f-f663-4ceb-be59-4f48ecea03a9
ms.date: 5/3/2018
ms.keywords: ReadPhysicalWithFlags, ReadPhysicalWithFlags function [Windows Debugging], WdbgExts_Ref_cf166083-f21a-4cfd-8daa-90c3f6bbcdcb.xml, debugger.readphysicalwithflags, wdbgexts/ReadPhysicalWithFlags
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	ReadPhysicalWithFlags
product:
- Windows
targetos: Windows
req.typenames: 
---

# ReadPhysicalWithFlags function


## -description


The <b>ReadPhysicalWithFlags</b> function reads from physical memory.


## -parameters




### -param address

Specifies the physical address to read.


### -param buf

Specifies the address of an array of bytes to hold the data that is read.


### -param size

Specifies the number of bytes to read. 


### -param flags

Specifies the properties of the physical memory to be read.  This must match the way the physical memory was advertised to the operating system on the target.  Possible values are listed in the following table.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
PHYS_FLAG_DEFAULT

</td>
<td>
Use the default memory caching.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_CACHED

</td>
<td>
The physical memory is cached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_UNCACHED

</td>
<td>
The physical memory is uncached.

</td>
</tr>
<tr>
<td>
PHYS_FLAG_WRITE_COMBINED

</td>
<td>
The physical memory is write-combined.

</td>
</tr>
</table>
 


### -param sizer

Receives the number of bytes actually read.


## -returns



None




## -remarks



If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554313">ReadPhysical</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561448">WritePhysicalWithFlags</a>
 

 

