---
UID: NF:wdbgexts.GetTypeSize
title: GetTypeSize function
author: windows-driver-content
description: The GetTypeSize function returns the size in the target's memory of an instance of the specified type.
old-location: debugger\gettypesize.htm
old-project: debugger
ms.assetid: 5532799d-5c3b-41ba-ab62-dca9c9d9eb56
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.gettypesize, wdbgexts/GetTypeSize, GetTypeSize function [Windows Debugging], GetTypeSize, WdbgExts_Ref_f3c7edf8-5c3b-440f-ace7-2081f9923d6f.xml
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




#### - Type [in]

Specifies the type to return the size of.


## -returns


This function returns the size of an instance of the specified type.


