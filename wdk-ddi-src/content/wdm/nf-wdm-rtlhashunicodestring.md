---
UID: NF:wdm.RtlHashUnicodeString
title: RtlHashUnicodeString function
author: windows-driver-content
description: The RtlHashUnicodeString routine creates a hash value from a given Unicode string and hash algorithm.
old-location: kernel\rtlhashunicodestring.htm
old-project: kernel
ms.assetid: 69a18c4a-9e28-47fb-9d2e-206d660eea6c
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: RtlHashUnicodeString, RtlHashUnicodeString routine [Kernel-Mode Driver Architecture], k109_090277b1-32f6-4c3d-b1fc-bacec35efc1d.xml, kernel.rtlhashunicodestring, wdm/RtlHashUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlHashUnicodeString
product: Windows
targetos: Windows
req.typenames: 
---

# RtlHashUnicodeString function


## -description


The <b>RtlHashUnicodeString </b>routine creates a hash value from a given Unicode string and hash algorithm.


## -parameters




### -param String [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure that contains the Unicode string to be converted to a hash value.


### -param CaseInSensitive [in]

Specifies whether to treat the Unicode string as case sensitive when computing the hash value. If <i>CaseInSensitive</i> is <b>TRUE</b>, a lowercase and uppercase string hash to the same value. 


### -param HashAlgorithm [in]

The hash algorithm to use. If <i>HashAlgorithm</i> is HASH_STRING_ALGORITHM_X65599, <b>RtlHashUnicodeString</b> uses the x65599 hashing algorithm. If <i>HashAlgorithm</i> is HASH_STRING_ALGORITHM_DEFAULT, <b>RtlHashUnicodeString</b> uses the default algorithm. Currently, the default algorithm is the x65599 hashing algorithm.


### -param HashValue [out]

A pointer to a ULONG variable that receives the hash value.


## -returns



<b>RtlHashUnicodeString</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS value on failure. The routine returns a STATUS_INVALID_PARAMETER value if the Unicode string is <b>NULL</b>, <i>HashValue</i> is <b>NULL</b>, or the caller specifies an undefined value for <i>HashAlgorithm</i>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

