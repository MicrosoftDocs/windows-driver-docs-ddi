---
UID: NF:wdbgexts.GetTypeSize
title: GetTypeSize function
author: windows-driver-content
description: The GetTypeSize function returns the size in the target's memory of an instance of the specified type.
old-location: debugger\gettypesize.htm
old-project: debugger
ms.assetid: 5532799d-5c3b-41ba-ab62-dca9c9d9eb56
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetTypeSize, GetTypeSize function [Windows Debugging], WdbgExts_Ref_f3c7edf8-5c3b-440f-ace7-2081f9923d6f.xml, debugger.gettypesize, wdbgexts/GetTypeSize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetTypeSize
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetTypeSize function


## -description


The <b>GetTypeSize</b> function returns the size in the target's memory of an instance of the specified type.


## -syntax


````
__inline ULONG GetTypeSize(
  _In_ LPCSTR Type
);
````


## -parameters




### -param Type [in]

Specifies the type to return the size of.


## -returns



This function returns the size of an instance of the specified type.



