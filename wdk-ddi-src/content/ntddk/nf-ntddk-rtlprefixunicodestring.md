---
UID: NF:ntddk.RtlPrefixUnicodeString
title: RtlPrefixUnicodeString function (ntddk.h)
description: The RtlPrefixUnicodeString routine compares two Unicode strings to determine whether one string is a prefix of the other.
old-location: kernel\rtlprefixunicodestring.htm
tech.root: kernel
ms.assetid: 9b26f4ed-6621-4dc5-8b60-9e4d3bf8d898
ms.date: 04/30/2018
ms.keywords: RtlPrefixUnicodeString, RtlPrefixUnicodeString routine [Kernel-Mode Driver Architecture], k109_b6130d6d-1a25-460b-a962-3b9353626768.xml, kernel.rtlprefixunicodestring, ntddk/RtlPrefixUnicodeString
f1_keywords:
 - "ntddk/RtlPrefixUnicodeString"
req.header: ntddk.h
req.include-header: Ntddk.h
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
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlPrefixUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlPrefixUnicodeString function


## -description


The <b>RtlPrefixUnicodeString</b> routine compares two Unicode strings to determine whether one string is a prefix of the other. 


## -parameters




### -param String1 [in]

Pointer to the first string, which might be a prefix of the buffered Unicode string at <i>String2</i>.


### -param String2 [in]

Pointer to the second string.


### -param CaseInSensitive [in]

If <b>TRUE</b>, case should be ignored when doing the comparison. 


## -returns



<b>RtlPrefixUnicodeString</b> returns <b>TRUE</b> if <i>String1</i> is a prefix of <i>String2</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcompareunicodestring">RtlCompareUnicodeString</a>
 

 

