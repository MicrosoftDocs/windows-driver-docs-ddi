---
UID: NF:dbgeng.IDebugSymbols4.GetFieldOffset
title: IDebugSymbols4::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset function returns the offset of a member from the beginning of a structure.
old-location: debugger\getfieldoffset.htm
tech.root: debugger
ms.assetid: 3e5e782b-1a72-446d-9d15-c0f513f3440c
ms.date: 1/19/2018
ms.keywords: WdbgExts_Ref_22c8a9bc-dec9-4eec-95c6-b265694b4385.xml, IDebugSymbols2::GetFieldOffset, IDebugSymbols::GetFieldOffset, IDebugSymbols4::GetFieldOffset, wdbgexts/GetFieldOffset, GetFieldOffset, IDebugSymbols2, IDebugSymbols4, GetFieldOffset function [Windows Debugging], debugger.getfieldoffset, IDebugSymbols
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
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---

# IDebugSymbols4::GetFieldOffset method


## -description


The <b>GetFieldOffset</b> function returns the offset of a member from the beginning of a structure.


## -syntax


```cpp
__inline ULONG GetFieldOffset(
  _In_  LPCSTR Type,
  _In_  LPCSTR Field,
  _Out_ PULONG pOffset
);
```


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


