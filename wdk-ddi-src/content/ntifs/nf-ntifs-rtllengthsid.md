---
UID: NF:ntifs.RtlLengthSid
title: RtlLengthSid function
author: windows-driver-content
description: The RtlLengthSid routine returns the length, in bytes, of a valid security identifier (SID).
old-location: ifsk\rtllengthsid.htm
old-project: ifsk
ms.assetid: 5d96061d-f1a2-4e45-b76e-5ada61d8accd
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: rtlref_8bbf6a04-413c-4f50-9f51-1ddd8bce58ff.xml, RtlLengthSid routine [Installable File System Drivers], ntifs/RtlLengthSid, RtlLengthSid, ifsk.rtllengthsid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	ntdll.dll
apiname:
-	RtlLengthSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlLengthSid function


## -description


The <b>RtlLengthSid</b> routine returns the length, in bytes, of a valid security identifier (SID). 


## -syntax


````
ULONG RtlLengthSid(
  _In_ PSID Sid
);
````


## -parameters




### -param Sid [in]

Pointer to the SID structure. Must point to a valid SID. 


## -returns



If the SID structure is valid, <b>RtlLengthSid</b> returns the length, in bytes, of the SID structure.

If the SID structure is not valid, the return value is undefined. Before calling <b>RtlLengthSid</b>, pass the SID to <a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a> to verify that it is valid. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



<a href="..\ntifs\nf-ntifs-rtllengthrequiredsid.md">RtlLengthRequiredSid</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>



<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlLengthSid routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

