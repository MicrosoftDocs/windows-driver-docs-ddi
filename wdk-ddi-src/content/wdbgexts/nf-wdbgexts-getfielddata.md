---
UID: NF:wdbgexts.GetFieldData
title: GetFieldData function
author: windows-driver-content
description: The GetFieldData function returns the value of a member in a structure.
old-location: debugger\getfielddata.htm
old-project: debugger
ms.assetid: e60c2288-fe25-4da5-9b17-6e95a30e7c1c
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: wdbgexts/GetFieldData, WdbgExts_Ref_898dacb4-308c-4a8f-99e2-030adf2b0eae.xml, GetFieldData, GetFieldData function [Windows Debugging], debugger.getfielddata
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
-	GetFieldData
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---

# GetFieldData function


## -description


The <b>GetFieldData</b> function returns the value of a member in a structure.


## -syntax


````
__inline ULONG GetFieldData(
  _In_  ULONG64 TypeAddress,
  _In_  LPCSTR  Type,
  _In_  LPCSTR  Field,
  _In_  ULONG   OutSize,
  _Out_ PVOID   pOutValue
);
````


## -parameters




### -param TypeAddress [in]

Specifies the address of the structure in the target's memory.


### -param Type [in]

Specifies the name of the type of the structure.  This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field [in]

Specifies the name of the member in the structure whose value will be returned.  Submembers can be specified by using a period-separated path, for example, "myfield.mysubfield".

If the size of the structure pointed to by <i>TypeAddress</i> is less than 8 bytes, <i>Field</i> can be <b>NULL</b>; in this case, the entire structure is copied to <i>pOutValue</i>.


### -param OutSize [in]

Specifies the size, in bytes, of the buffer <i>pOutValue</i>.

If <i>OutSize</i> is smaller than the size of the value returned, an error message is printed and an exception is raised; if the exception is handled or ignored, the return value is zero. In this case, the data beyond the end of the buffer referred to by <i>pOutValue</i> might be overwritten.


### -param pOutValue [out]

Receives the value of the member.  Or, the value of the type, if <i>Field</i> is <b>NULL</b>.


## -returns


If the function succeeds, the return value is zero. Otherwise, the return value is an <a href="https://msdn.microsoft.com/41d64bbc-cefe-4665-b054-e6bd135ccd20">IG_DUMP_SYMBOL_INFO error code</a>. 



