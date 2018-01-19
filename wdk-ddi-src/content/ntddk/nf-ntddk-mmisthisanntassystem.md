---
UID: NF:ntddk.MmIsThisAnNtAsSystem
title: MmIsThisAnNtAsSystem function
author: windows-driver-content
description: The MmIsThisAnNtAsSystem routine is obsolete for Windows XP and later versions of Windows. Use RtlGetVersion or RtlVerifyVersionInfo instead.
old-location: kernel\mmisthisanntassystem.htm
old-project: kernel
ms.assetid: e9daafb1-16ec-4ffe-b863-6f07c4b2a9b7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmIsThisAnNtAsSystem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete for Windows XP and later versions of Windows. Use RtlGetVersion or RtlVerifyVersionInfo instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmIsThisAnNtAsSystem
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# MmIsThisAnNtAsSystem function



## -description
The <b>MmIsThisAnNtAsSystem</b> routine is <u>obsolete</u> for Windows XP and later versions of Windows. Use <a href="..\wdm\nf-wdm-rtlgetversion.md">RtlGetVersion</a> or <a href="..\wdm\nf-wdm-rtlverifyversioninfo.md">RtlVerifyVersionInfo</a> instead.

The <b>MmIsThisAnNtAsSystem </b>routine checks whether the current platform is running a server version of the NT-based operating system.



## -syntax

````
BOOLEAN MmIsThisAnNtAsSystem(void);
````


## -parameters


## -returns
If the current platform is a server, <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>. 

If the current platform is a server, <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>. 

If the current platform is a server, <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>. 


## -remarks
Drivers can use this routine during initialization, along with <b>MmQuerySystemSize</b>, for sizing estimates of how many resources to allocate. For example, if <b>MmIsThisAnNtAsSystem</b> returns <b>TRUE</b>, the caller can increase the number of threads or the number of initially allocated entries for a lookaside list that it creates in medium and large systems. 


## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-mmquerysystemsize.md">MmQuerySystemSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmIsThisAnNtAsSystem routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

