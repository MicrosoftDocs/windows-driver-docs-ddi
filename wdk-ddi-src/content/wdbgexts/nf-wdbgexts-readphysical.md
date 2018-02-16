---
UID: NF:wdbgexts.ReadPhysical
title: ReadPhysical function
author: windows-driver-content
description: The ReadPhysical function reads from physical memory.
old-location: debugger\readphysical.htm
old-project: debugger
ms.assetid: 02ca3358-7740-4eda-ab7c-f4b8a88389c2
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.readphysical, ReadPhysical, wdbgexts/ReadPhysical, WdbgExts_Ref_4eaa6edb-2297-4454-b4aa-ea69aa5a073c.xml, ReadPhysical function [Windows Debugging]
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
-	ReadPhysical
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReadPhysical function


## -description


The <b>ReadPhysical</b> function reads from physical memory.


## -syntax


````
__inline VOID ReadPhysical(
   ULONG64 address,
   PVOID   buf,
   ULONG   size,
   PULONG  sizer
);
````


## -parameters




### -param address

Specifies the physical address to read.


### -param buf

Specifies the address of an array of bytes to hold the data that is read.


### -param size

Specifies the number of bytes to read. 


### -param sizer

Receives the number of bytes actually read.


## -returns



None




## -remarks



If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).




