---
UID: NF:ntifs.RtlInitializeSidEx
title: RtlInitializeSidEx function
author: windows-driver-content
description: The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure.
old-location: ifsk\rtlinitializesidex.htm
old-project: ifsk
ms.assetid: 367D8BC1-07F4-474E-913A-5F825320A70C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlInitializeSidEx, RtlInitializeSidEx routine [Installable File System Drivers], ifsk.rtlinitializesidex, ntifs/RtlInitializeSidEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows 10 and later.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInitializeSidEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlInitializeSidEx function


## -description


The <b>RtlInitializeSidEx</b> routine initializes a pre-allocated security identifier (SID) structure. 


## -parameters




### -param Sid [out]

Pointer to a caller-allocated SID structure to be initialized. 


### -param IdentifierAuthority [in]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556743">SID_IDENTIFIER_AUTHORITY</a> structure to set in the SID structure. 


### -param SubAuthorityCount [in]

Number of sub-authorities to set in the SID.


### -param param

TBD




####### - ...

The values to set each sub-authority. The caller must specify the SubAuthorityCount argument.


## -returns



<b>RtlInitializeSid</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The SID was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>SubAuthorityCount</i> value is invalid.

</td>
</tr>
</table>
 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553236">RtlSubAuthoritySid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556740">SID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556743">SID_IDENTIFIER_AUTHORITY</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeSidEx routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

