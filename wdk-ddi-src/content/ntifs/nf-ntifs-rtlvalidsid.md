---
UID: NF:ntifs.RtlValidSid
title: RtlValidSid function
author: windows-driver-content
description: The RtlValidSid routine validates a security identifier (SID) by verifying that the revision number is within a known range and that the number of subauthorities is less than the maximum.
old-location: ifsk\rtlvalidsid.htm
old-project: ifsk
ms.assetid: d4579703-0d51-4e23-b458-b2be43951dac
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlValidSid routine [Installable File System Drivers], rtlref_8d79344c-bb78-433f-be34-84e314b232a0.xml, RtlValidSid, ifsk.rtlvalidsid, ntifs/RtlValidSid
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlValidSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlValidSid function


## -description


The <b>RtlValidSid</b> routine validates a security identifier (SID) by verifying that the revision number is within a known range and that the number of subauthorities is less than the maximum. 


## -syntax


````
BOOLEAN RtlValidSid(
  _In_ PSID Sid
);
````


## -parameters




### -param Sid [in]

Pointer to the SID structure to validate. 


## -returns


<b>RtlValidSid</b> returns <b>TRUE</b> if the security descriptor is valid, <b>FALSE</b> otherwise. 



## -remarks


For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 



## -see-also

<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>

<a href="..\ntifs\nf-ntifs-rtllengthsid.md">RtlLengthSid</a>

<a href="..\ntifs\nf-ntifs-rtllengthrequiredsid.md">RtlLengthRequiredSid</a>

<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>

<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlValidSid routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

