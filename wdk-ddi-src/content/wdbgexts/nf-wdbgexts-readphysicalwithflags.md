---
UID: NF:wdbgexts.ReadPhysicalWithFlags
title: ReadPhysicalWithFlags function
author: windows-driver-content
description: The ReadPhysicalWithFlags function reads from physical memory.
old-location: debugger\readphysicalwithflags.htm
old-project: debugger
ms.assetid: 7ff5787f-f663-4ceb-be59-4f48ecea03a9
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: WdbgExts_Ref_cf166083-f21a-4cfd-8daa-90c3f6bbcdcb.xml, ReadPhysicalWithFlags function [Windows Debugging], debugger.readphysicalwithflags, ReadPhysicalWithFlags, wdbgexts/ReadPhysicalWithFlags
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	ReadPhysicalWithFlags
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReadPhysicalWithFlags function


## -description


The <b>ReadPhysicalWithFlags</b> function reads from physical memory.


## -syntax


````
__inline VOID ReadPhysicalWithFlags(
   ULONG64 address,
   PVOID   buf,
   ULONG   size,
   ULONG   flags,
   PULONG  sizer
);
````


## -parameters




#### - address

Specifies the physical address to read.


#### - buf

Specifies the address of an array of bytes to hold the data that is read.


#### - size

Specifies the number of bytes to read. 


#### - flags

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


#### - sizer

Receives the number of bytes actually read.


## -returns


None



## -remarks


If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).




## -see-also

<a href="..\wdbgexts\nf-wdbgexts-writephysicalwithflags.md">WritePhysicalWithFlags</a>

<a href="..\wdbgexts\nf-wdbgexts-readphysical.md">ReadPhysical</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ReadPhysicalWithFlags function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

