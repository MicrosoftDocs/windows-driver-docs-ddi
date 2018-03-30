---
UID: NF:wdbgexts.GetCurrentProcessHandle
title: GetCurrentProcessHandle function
author: windows-driver-content
description: The GetCurrentProcessHandle function returns the system handle for the current process.
old-location: debugger\getcurrentprocesshandle.htm
old-project: debugger
ms.assetid: b6780f1c-e093-4d91-8909-dabb1ecaefaa
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetCurrentProcessHandle, GetCurrentProcessHandle function [Windows Debugging], WdbgExts_Ref_50cc8e27-7f7e-4ec3-ad2d-745f38e87037.xml, debugger.getcurrentprocesshandle, wdbgexts/GetCurrentProcessHandle
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
-	GetCurrentProcessHandle
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetCurrentProcessHandle function


## -description


The <b>GetCurrentProcessHandle</b> function returns the system handle for the current process.


## -parameters




### -param hp

Receives the system handle for the current process.


## -returns



None




## -remarks



In kernel-mode debugging, the only process in the target is the virtual process created for the kernel. In this case, an artificial handle is created. The artificial handle can only be used with the debugger.



