---
UID: NF:wdbgexts.WriteMsr
title: WriteMsr function
author: windows-driver-content
description: The WriteMsr function writes to a Model-Specific Register (MSR).
old-location: debugger\writemsr.htm
old-project: debugger
ms.assetid: a88c2c74-ab9a-4d9a-aeb7-d08bfe497da4
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: WriteMsr function [Windows Debugging], dbgeng/WriteMsr, WdbgExts_Ref_faeb78e1-24a2-4210-94f9-4e468ba69181.xml, WriteMsr, debugger.writemsr
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
-	dbgeng.h
apiname:
-	WriteMsr
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# WriteMsr function


## -description


The <b>WriteMsr</b> function writes to a Model-Specific Register (MSR). 


## -syntax


````
__inline VOID WriteMsr(
  _In_ ULONG   MsrReg,
  _In_ ULONG64 MsrValue
);
````


## -parameters




### -param MsrReg [in]

Specifies the ID number of the MSR.


### -param MsrValue [in]

Specifies the new value of the MSR.


## -returns


None



## -remarks


For a WdbgExts extension, include wdbgexts.h. For a DbgEng extension, include wdbgexts.h before dbgeng.h. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.


