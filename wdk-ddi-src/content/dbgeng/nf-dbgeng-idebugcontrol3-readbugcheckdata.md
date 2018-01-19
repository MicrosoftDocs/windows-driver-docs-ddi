---
UID: NF:dbgeng.IDebugControl3.ReadBugCheckData
title: IDebugControl3::ReadBugCheckData method
author: windows-driver-content
description: The ReadBugCheckData method reads the kernel bug check code and related parameters.
old-location: debugger\readbugcheckdata.htm
old-project: debugger
ms.assetid: 3ede32f5-9671-4f38-a33f-96536300267b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::ReadBugCheckData, ReadBugCheckData
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
req.alt-api: IDebugControl.ReadBugCheckData,IDebugControl2.ReadBugCheckData,IDebugControl3.ReadBugCheckData
req.alt-loc: dbgeng.h
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugControl3::ReadBugCheckData method



## -description
The <b>ReadBugCheckData</b> method reads the kernel bug check code and related parameters.



## -syntax

````
HRESULT ReadBugCheckData(
  [out] PULONG   Code,
  [out] PULONG64 Arg1,
  [out] PULONG64 Arg2,
  [out] PULONG64 Arg3,
  [out] PULONG64 Arg4
);
````


## -parameters

### -param Code [out]

Receives the bug check code.


### -param Arg1 [out]

Receives the first parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.


### -param Arg2 [out]

Receives the second parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.


### -param Arg3 [out]

Receives the third parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.


### -param Arg4 [out]

Receives the fourth parameter associated with the bug check.  The interpretation of this parameter depends on the bug check code.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
This method is only available in kernel-mode debugging.

For more information about bug checks, including a list of bug check codes and their interpretations, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450912">Bug Checks (Blue Screens)</a>.</p>