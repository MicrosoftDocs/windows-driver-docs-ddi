---
UID: NF:wdm.RtlSecureZeroMemory
title: RtlSecureZeroMemory function
author: windows-driver-content
description: The RtlSecureZeroMemory routine fills a block of memory with zeros in a way that is guaranteed to be secure.
old-location: kernel\rtlsecurezeromemory.htm
old-project: kernel
ms.assetid: b7a9beaf-5eca-4fb0-af63-06c002297085
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k109_8bcffbc1-2930-416b-a192-b70c477d1910.xml, RtlSecureZeroMemory, wdm/RtlSecureZeroMemory, kernel.rtlsecurezeromemory, RtlSecureZeroMemory routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows. (Because the routine is declared inline, the body of the routine can be included in earlier versions of the operating system.)
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	RtlSecureZeroMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlSecureZeroMemory function


## -description


The <b>RtlSecureZeroMemory</b> routine fills a block of memory with zeros in a way that is guaranteed to be secure.


## -syntax


````
PVOID RtlSecureZeroMemory(
  _Out_ PVOID  ptr,
  _In_  SIZE_T cnt
);
````


## -parameters




#### - ptr [out]

Pointer to the memory buffer to be filled with zeros.


#### - cnt [in]

Specifies the number of bytes to be filled with zeros.


## -returns


None



## -remarks


The effect of <b>RtlSecureZeroMemory</b> is identical to that of <a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>, except that it is guaranteed to zero the memory location, even if it is not subsequently written to. (The compiler can optimize away a call to <b>RtlZeroMemory</b>, if it determines that the caller does not access that memory range again.)

Use <b>RtlSecureZeroMemory</b> to guarantee that sensitive information has been zeroed out. For example, suppose that a function uses a local array variable to store password information. Once the function exits, the password information can remain in the same memory location unless zeroed out by <b>RtlSecureZeroMemory</b>.

<b>RtlSecureZeroMemory</b> is slower than <b>RtlZeroMemory</b>; therefore, if security is not an issue, use <b>RtlZeroMemory</b> instead.

Callers of <b>RtlSecureZeroMemory</b> can be running at any IRQL if the <i>ptr</i> block is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.



## -see-also

<a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>

<a href="..\wdm\nf-wdm-rtlfillmemory.md">RtlFillMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlSecureZeroMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

