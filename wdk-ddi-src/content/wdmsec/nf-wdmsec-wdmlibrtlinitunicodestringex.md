---
UID: NF:wdmsec.WdmlibRtlInitUnicodeStringEx
title: WdmlibRtlInitUnicodeStringEx function
author: windows-driver-content
description: The WdmlibRtlInitUnicodeStringEx function initializes a counted string of Unicode characters.
old-location: kernel\wdmlibrtlinitunicodestringex.htm
old-project: kernel
ms.assetid: 79DEDC5B-2A9B-4493-9CB3-7290BEBBD291
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdmsec/RtlInitUnicodeString, kernel.wdmlibrtlinitunicodestringex, WdmlibRtlInitUnicodeStringEx, wdmsec/WdmlibRtlInitUnicodeStringEx, WdmlibRtlInitUnicodeStringEx function [Kernel-Mode Driver Architecture], RtlInitUnicodeString
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	NtosKrnl.exe
apiname: 
-	WdmlibRtlInitUnicodeStringEx
-	RtlInitUnicodeString
product: Windows
targetos: Windows
req.typenames: *PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM
req.product: Windows 10 or later.
---

# WdmlibRtlInitUnicodeStringEx function


## -description


The <b>WdmlibRtlInitUnicodeStringEx</b> function initializes a counted string of Unicode characters.


## -syntax


````
NTSTATUS WdmlibRtlInitUnicodeStringEx(
  _Out_    PUNICODE_STRING DestinationString,
  _In_opt_ PCWSTR          SourceString
);
````


## -parameters




### -param DestinationString [out]

A pointer to the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to be initialized.


### -param SourceString [in, optional]

A pointer to a null-terminated wide-character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## -remarks


The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>WdmlibRtlInitUnicodeStringEx</b> does not alter the source string pointed to by <i>SourceString</i>.
<div class="alert"><b>Note</b>  If the source string is longer than MAX_USTRING - 1 bytes, <b>WdmlibRtlInitUnicodeStringEx</b> sets the <b>Length</b> member of the <b>UNICODE_STRING</b> structure pointed to by <i>DestinationString</i> to MAX_USTRING - 2, and sets the <b>MaximumLength</b> member of this structure to MAX_USTRING.  In this case, the <b>Length</b> and <b>MaximumLength</b> values misrepresent the length of the null-terminated source string, and relying on the accuracy of these values is potentially dangerous.</div><div> </div>Callers of <b>WdmlibRtlInitUnicodeStringEx</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.



## -see-also

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinitex.md">RtlUnicodeStringInitEx</a>

<a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WdmlibRtlInitUnicodeStringEx function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

