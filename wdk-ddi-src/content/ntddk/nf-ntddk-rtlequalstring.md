---
UID: NF:ntddk.RtlEqualString
title: RtlEqualString function
author: windows-driver-content
description: The RtlEqualString routine compares two counted strings to determine whether they are equal.
old-location: kernel\rtlequalstring.htm
old-project: kernel
ms.assetid: f8244276-0cf6-4315-9f4a-85890194dad8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlEqualString, RtlEqualString routine [Kernel-Mode Driver Architecture], k109_67ef861f-4f4b-4e98-be53-8962b02df08e.xml, kernel.rtlequalstring, ntddk/RtlEqualString
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlEqualString
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlEqualString function


## -description


The <b>RtlEqualString</b> routine compares two counted strings to determine whether they are equal.


## -syntax


````
BOOLEAN RtlEqualString(
  _In_ const STRING  *String1,
  _In_ const STRING  *String2,
  _In_       BOOLEAN CaseInSensitive
);
````


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

<a href="..\wudfwdm\nf-wudfwdm-rtlequalunicodestring.md">RtlEqualUnicodeString</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlEqualString routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

