---
UID: NF:wdm.RtlCopyUnicodeString
title: RtlCopyUnicodeString function (wdm.h)
description: The RtlCopyUnicodeString routine copies a source string to a destination string.
old-location: kernel\rtlcopyunicodestring.htm
tech.root: kernel
ms.assetid: 241801a5-4a02-46f3-a007-f571d58c7825
ms.date: 04/30/2018
ms.keywords: RtlCopyUnicodeString, RtlCopyUnicodeString routine [Kernel-Mode Driver Architecture], k109_5d0b341c-a440-4137-bdc3-77e0da0db58c.xml, kernel.rtlcopyunicodestring, wdm/RtlCopyUnicodeString
ms.topic: function
f1_keywords:
 - "wdm/RtlCopyUnicodeString"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
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
req.irql: Any level (See Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
- Ntdll.dll
api_name:
- RtlCopyUnicodeString
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlCopyUnicodeString function


## -description


The <b>RtlCopyUnicodeString</b> routine copies a source string to a destination string.


## -parameters




### -param DestinationString [in, out]

A pointer to the destination string buffer. This parameter points to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure. 


### -param SourceString [in, optional]

A pointer to the source string buffer. This parameter points to a <b>UNICODE_STRING</b> structure. 


## -returns



None




## -remarks



If <i>SourceString</i> is <b>NULL</b>, this routine sets the <b>Length</b> field of the structure pointed to by <i>DestinationString</i> to zero.

This routine does not modify the <b>MaximumLength</b> and <b>Buffer</b> fields of the structure pointed to by <i>DestinationString</i>.

The number of bytes copied from the source string is either the source string length (specified by the <b>Length</b> member of the structure pointed to by <i>SourceString</i>) or the maximum length of the destination string (specified by the <b>MaximumLength</b> member of the structure pointed to by <i>DestinationString</i>), whichever is smaller.

The caller must properly initialize all members of the structure pointed to by <i>DestinationString</i> before calling <b>RtlCopyUnicodeString</b>. Failure to initialize the <b>Length</b> or the <b>MaximumLength</b> member before calling this routine can cause a buffer overrun.

The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL >= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlcopystring">RtlCopyString</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

