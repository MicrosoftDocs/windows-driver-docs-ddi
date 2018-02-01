---
UID: NF:wdbgexts.ReadMsr
title: ReadMsr function
author: windows-driver-content
description: The ReadMsr function reads the contents of a Model-Specific Register (MSR).
old-location: debugger\readmsr.htm
old-project: debugger
ms.assetid: 1cb51f88-a943-43e6-af18-0e9e301d8382
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.readmsr, ReadMsr function [Windows Debugging], ReadMsr, wdbgexts/ReadMsr, WdbgExts_Ref_37577d05-a60b-4064-850a-d73616d93f37.xml
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
-	ReadMsr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# ReadMsr function


## -description


The <b>ReadMsr</b> function reads the contents of a Model-Specific Register (MSR). 


## -syntax


````
__inline VOID ReadMsr(
   ULONG     MsrReg,
   ULONGLONG *MsrValue
);
````


## -parameters




### -param MsrReg

Specifies the ID number of the MSR.


### -param MsrValue

Receives the value of the MSR.


## -returns


None



## -remarks


If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).



