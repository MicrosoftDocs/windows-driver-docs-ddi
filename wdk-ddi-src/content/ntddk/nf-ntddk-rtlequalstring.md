---
UID: NF:ntddk.RtlEqualString
title: RtlEqualString function
description: The RtlEqualString routine compares two counted strings to determine whether they are equal.
old-location: kernel\rtlequalstring.htm
tech.root: kernel
ms.assetid: f8244276-0cf6-4315-9f4a-85890194dad8
ms.date: 04/30/2018
ms.keywords: RtlEqualString, RtlEqualString routine [Kernel-Mode Driver Architecture], k109_67ef861f-4f4b-4e98-be53-8962b02df08e.xml, kernel.rtlequalstring, ntddk/RtlEqualString
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlEqualString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlEqualString function


## -description


The <b>RtlEqualString</b> routine compares two counted strings to determine whether they are equal.


## -parameters




### -param String1 [in]

Pointer to the first string.


### -param String2 [in]

Pointer to the second string.


### -param CaseInSensitive [in]

If <b>TRUE</b>, case should be ignored when doing the comparison. 


## -returns



<b>RtlEqualString</b> returns <b>TRUE</b> if the two strings are equal, otherwise it returns <b>FALSE</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561854">RtlEqualUnicodeString</a>
 

 

