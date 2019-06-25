---
UID: NF:wdbgexts.GetTebAddress
title: GetTebAddress function (wdbgexts.h)
description: The GetTebAddress function returns the address of the thread environment block (TEB) for the current operating system thread.
old-location: debugger\gettebaddress.htm
tech.root: debugger
ms.assetid: 6dbe7da6-31f6-43f2-aa25-be6f13c8d8d8
ms.date: 05/03/2018
ms.keywords: GetTebAddress, GetTebAddress function [Windows Debugging], WdbgExts_Ref_69ad127f-7df4-4c57-9475-55040aa02f78.xml, debugger.gettebaddress, wdbgexts/GetTebAddress
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdbgexts.h
api_name:
- GetTebAddress
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetTebAddress function


## -description


The <b>GetTebAddress</b> function returns the address of the thread environment block (TEB) for the current operating system thread.


## -parameters




### -param Address

Receives the address of the TEB for the current operating system thread.


## -returns



None




## -remarks



In user-mode debugging, the TEB for the current thread is returned.  In kernel-mode debugging, the TEB for the operating system thread that was running on the current processor when the last event occurred is returned.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdbgexts/nf-wdbgexts-getpebaddress">GetPebAddress</a>
 

 

