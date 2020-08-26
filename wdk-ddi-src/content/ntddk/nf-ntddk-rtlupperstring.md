---
UID: NF:ntddk.RtlUpperString
title: RtlUpperString function (ntddk.h)
description: The RtlUpperString routine copies the given SourceString to the DestinationString buffer, converting it to uppercase.
old-location: kernel\rtlupperstring.htm
tech.root: kernel
ms.assetid: 3a120831-deac-4075-9aa7-8ae39ac29363
ms.date: 04/30/2018
keywords: ["RtlUpperString function"]
ms.keywords: RtlUpperString, RtlUpperString routine [Kernel-Mode Driver Architecture], k109_07df2cdb-0d52-4094-bcdf-62977c15e098.xml, kernel.rtlupperstring, ntddk/RtlUpperString
f1_keywords:
 - "ntddk/RtlUpperString"
 - "RtlUpperString"
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
req.irql: <=APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- RtlUpperString
targetos: Windows
req.typenames: 
---

# RtlUpperString function


## -description


The <b>RtlUpperString</b> routine copies the given <i>SourceString</i> to the <i>DestinationString</i> buffer, converting it to uppercase.


## -parameters




### -param DestinationString 
[in, out]
Pointer to the buffer for the converted destination string. 


### -param SourceString 
[in]
Pointer to the source string to be converted to uppercase. 


## -returns



None




## -remarks



The <b>MaximumLength</b> and <b>Buffer</b> members of <i>DestinationString</i> are not modified by this routine.

The number of bytes copied from <i>SourceString</i> is either the <b>Length</b> of <i>SourceString</i> or the <b>MaximumLength</b> of <i>DestinationString</i>, whichever is smaller. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlupperchar">RtlUpperChar</a>
 

 

