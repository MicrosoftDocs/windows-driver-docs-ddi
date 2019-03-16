---
UID: NF:ntddk.RtlCharToInteger
title: RtlCharToInteger function (ntddk.h)
description: The RtlCharToInteger routine converts a single-byte character string to an integer value in the specified base.
old-location: kernel\rtlchartointeger.htm
tech.root: kernel
ms.assetid: a08cb12a-c574-4871-9bba-f8f3a766f377
ms.date: 04/30/2018
ms.keywords: RtlCharToInteger, RtlCharToInteger routine [Kernel-Mode Driver Architecture], k109_0c8d9b78-6363-4884-a475-4f402ea3643a.xml, kernel.rtlchartointeger, ntddk/RtlCharToInteger
ms.topic: function
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
- RtlCharToInteger
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCharToInteger function


## -description


The <b>RtlCharToInteger</b> routine converts a single-byte character string to an integer value in the specified base. 


## -parameters




### -param String [in]

Pointer to a null-terminated, single-byte character string. 


### -param Base [in, optional]

Specifies decimal, binary, octal, or hexadecimal base. If this parameter is not given, the routine will look for 0x, 0o, and 0b prefixes in the input string to determine if the base should be decimal (default), binary, octal, or hexadecimal.


### -param Value [out]

Pointer to a location to which the converted value is returned. 


## -returns



<b>RtlCharToInteger</b> returns STATUS_SUCCESS if the given character string is converted. Otherwise, it can return STATUS_INVALID_PARAMETER. 




## -remarks



<b>RtlCharToInteger</b> converts ANSI alphanumeric characters. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561929">RtlInitString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561941">RtlIntegerToUnicodeString</a>
 

 

