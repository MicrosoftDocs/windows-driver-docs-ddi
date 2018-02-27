---
UID: NF:wdm.RtlInitStringEx
title: RtlInitStringEx function
author: windows-driver-content
description: The RtlInitStringEx routine initializes a counted string of 8-bit characters.
old-location: kernel\rtl_init_string_ex.htm
old-project: kernel
ms.assetid: D59E6B78-2B51-4A5D-A9EA-E6D8DD90C374
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: RtlInitString, RtlInitString routine [Kernel-Mode Driver Architecture], RtlInitStringEx, kernel.rtl_init_string_ex, wdm/RtlInitString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
-	RtlInitString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlInitStringEx function


## -description


The <b>RtlInitStringEx</b> routine initializes a counted string of 8-bit characters.


## -syntax


````
NTSTATUS RtlInitString(
  _Out_    PSTRING DestinationString,
  _In_opt_ PCSZ    SourceString
);
````


## -parameters




### -param DestinationString [out]

A pointer to the <b>STRING</b> structure to be initialized. The Ntdef.h header file defines this structure to be identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure.


### -param SourceString [in, optional]

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## -returns



Returns STATUS_NAME_TOO_LONG if the SourceString is too long. Otherwise, this routine returns STATUS_SUCCESS.




## -remarks



This routine initializes a counted character string.

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <b>STRING</b> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitStringEx</b> does not alter the source string pointed to by <i>SourceString</i>.

Callers of <b>RtlInitStringEx</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitStringEx routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

