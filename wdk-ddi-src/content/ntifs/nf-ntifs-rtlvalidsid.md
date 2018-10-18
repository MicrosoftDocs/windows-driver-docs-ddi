---
UID: NF:ntifs.RtlValidSid
title: RtlValidSid function
author: windows-driver-content
description: The RtlValidSid routine validates a security identifier (SID) by verifying that the revision number is within a known range and that the number of subauthorities is less than the maximum.
old-location: ifsk\rtlvalidsid.htm
tech.root: ifsk
ms.assetid: d4579703-0d51-4e23-b458-b2be43951dac
ms.date: 4/16/2018
ms.keywords: RtlValidSid, RtlValidSid routine [Installable File System Drivers], ifsk.rtlvalidsid, ntifs/RtlValidSid, rtlref_8d79344c-bb78-433f-be34-84e314b232a0.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlValidSid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlValidSid function


## -description


The <b>RtlValidSid</b> routine validates a security identifier (SID) by verifying that the revision number is within a known range and that the number of subauthorities is less than the maximum. 


## -parameters




### -param Sid [in]

Pointer to the SID structure to validate. 


## -returns



<b>RtlValidSid</b> returns <b>TRUE</b> if the security descriptor is valid, <b>FALSE</b> otherwise. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552256">RtlEqualPrefixSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552260">RtlEqualSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552998">RtlInitializeSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553083">RtlLengthRequiredSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553085">RtlLengthSid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553236">RtlSubAuthoritySid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>
 

 

