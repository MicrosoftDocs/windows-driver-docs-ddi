---
UID: NF:wdmsec.WdmlibRtlInitUnicodeStringEx
title: WdmlibRtlInitUnicodeStringEx function
author: windows-driver-content
description: The WdmlibRtlInitUnicodeStringEx function initializes a counted string of Unicode characters.
old-location: kernel\wdmlibrtlinitunicodestringex.htm
old-project: kernel
ms.assetid: 79DEDC5B-2A9B-4493-9CB3-7290BEBBD291
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlInitUnicodeString, WdmlibRtlInitUnicodeStringEx, WdmlibRtlInitUnicodeStringEx function [Kernel-Mode Driver Architecture], kernel.wdmlibrtlinitunicodestringex, wdmsec/RtlInitUnicodeString, wdmsec/WdmlibRtlInitUnicodeStringEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdmsec.h
req.include-header: Wdmsec.h, Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	WdmlibRtlInitUnicodeStringEx
-	RtlInitUnicodeString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_ITEM, *PWORK_QUEUE_ITEM
req.product: Windows 10 or later.
---

# WdmlibRtlInitUnicodeStringEx function


## -description


The <b>WdmlibRtlInitUnicodeStringEx</b> function initializes a counted string of Unicode characters.


## -parameters




### -param DestinationString [out]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure to be initialized.


### -param SourceString [in, optional]

A pointer to a null-terminated wide-character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## -remarks



The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>WdmlibRtlInitUnicodeStringEx</b> does not alter the source string pointed to by <i>SourceString</i>.

<div class="alert"><b>Note</b>  If the source string is longer than MAX_USTRING - 1 bytes, <b>WdmlibRtlInitUnicodeStringEx</b> sets the <b>Length</b> member of the <b>UNICODE_STRING</b> structure pointed to by <i>DestinationString</i> to MAX_USTRING - 2, and sets the <b>MaximumLength</b> member of this structure to MAX_USTRING.  In this case, the <b>Length</b> and <b>MaximumLength</b> values misrepresent the length of the null-terminated source string, and relying on the accuracy of these values is potentially dangerous.</div>
<div> </div>
Callers of <b>WdmlibRtlInitUnicodeStringEx</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562954">RtlUnicodeStringInit</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562958">RtlUnicodeStringInitEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>
 

 

