---
UID: NF:dbgeng.IDebugSymbols5.GetFieldOffset
title: IDebugSymbols5::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset function returns the offset of a member from the beginning of a structure.
old-location: debugger\getfieldoffset.htm
tech.root: debugger
ms.assetid: 3e5e782b-1a72-446d-9d15-c0f513f3440c
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.getfieldoffset, IDebugSymbols4::GetFieldOffset, WdbgExts_Ref_22c8a9bc-dec9-4eec-95c6-b265694b4385.xml, IDebugSymbols4, IDebugSymbols::GetFieldOffset, GetFieldOffset function [Windows Debugging], IDebugSymbols5::GetFieldOffset, wdbgexts/GetFieldOffset, GetFieldOffset, IDebugSymbols5, IDebugSymbols
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
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
req.lib: dbgeng.h
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
-	GetFieldOffset
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols5::GetFieldOffset method


## -description


The <b>GetFieldOffset</b> function returns the offset of a member from the beginning of a structure.


## -syntax


````
__inline ULONG GetFieldOffset(
  _In_  LPCSTR Type,
  _In_  LPCSTR Field,
  _Out_ PULONG pOffset
);
````


## -parameters




### -param Module




### -param TypeId




### -param Field [in]

Specifies the name of the member in the structure.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".


### -param Offset





#### - Type [in]

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


#### - pOffset [out]

Receives the offset of the member from the beginning of an instance of the structure.


## -returns


If the function succeeds, the return value is zero. Otherwise, the return value is an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>.


