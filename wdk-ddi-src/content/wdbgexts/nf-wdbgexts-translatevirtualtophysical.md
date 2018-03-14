---
UID: NF:wdbgexts.TranslateVirtualToPhysical
title: TranslateVirtualToPhysical function
author: windows-driver-content
description: The TranslateVirtualToPhysical function translates a virtual memory address into a physical memory address.
old-location: debugger\translatevirtualtophysical.htm
old-project: debugger
ms.assetid: 803f766a-e02f-4b9c-bfe0-6197e0f2855c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: TranslateVirtualToPhysical, TranslateVirtualToPhysical function [Windows Debugging], WdbgExts_Ref_ec3ff314-8800-4f77-a40e-e127e6cf0133.xml, debugger.translatevirtualtophysical, wdbgexts/TranslateVirtualToPhysical
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
-	TranslateVirtualToPhysical
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# TranslateVirtualToPhysical function


## -description


The <b>TranslateVirtualToPhysical</b> function translates a virtual memory address into a physical memory address.


## -syntax


````
__inline BOOL TranslateVirtualToPhysical(
   ULONG64 Virtual,
   ULONG64 *Physical
);
````


## -parameters




### -param Virtual

Specifies the virtual memory address to translate.


### -param Physical

Receives the physical memory address.


## -returns



If the function succeeds, the return value is <b>TRUE</b>; otherwise, it is <b>FALSE</b>.




## -remarks



This function is only available in kernel-mode debugging.

If you are writing a WdbgExts extension, include wdbgexts.h. If you are writing a DbgEng extension that calls this function, include wdbgexts.h before dbgeng.h (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details.)



