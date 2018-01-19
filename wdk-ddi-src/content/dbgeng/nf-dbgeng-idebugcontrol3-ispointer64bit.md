---
UID: NF:dbgeng.IDebugControl3.IsPointer64Bit
title: IDebugControl3::IsPointer64Bit method
author: windows-driver-content
description: The IsPointer64Bit method determines if the effective processor uses 64-bit pointers.
old-location: debugger\ispointer64bit.htm
old-project: debugger
ms.assetid: 01003268-844e-4613-ac13-0306396e56b9
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugControl3, IDebugControl3::IsPointer64Bit, IsPointer64Bit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugControl.IsPointer64Bit,IDebugControl2.IsPointer64Bit,IDebugControl3.IsPointer64Bit
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

# IDebugControl3::IsPointer64Bit method



## -description
The <b>IsPointer64Bit</b> method determines if the effective processor uses 64-bit pointers.



## -syntax

````
HRESULT IsPointer64Bit();
````


## -parameters


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The effective processor uses 64-bit pointers.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The effective processor does not use 64-bit pointers.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The effective processor uses 64-bit pointers.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The effective processor does not use 64-bit pointers.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The effective processor uses 64-bit pointers.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The effective processor does not use 64-bit pointers.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
