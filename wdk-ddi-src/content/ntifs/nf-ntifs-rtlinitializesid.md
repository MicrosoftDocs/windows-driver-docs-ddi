---
UID: NF:ntifs.RtlInitializeSid
title: RtlInitializeSid function
author: windows-driver-content
description: The RtlInitializeSid routine initializes a security identifier (SID) structure.
old-location: ifsk\rtlinitializesid.htm
old-project: ifsk
ms.assetid: 6b87483f-8d5e-4e1d-839d-2271990dcbaa
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlInitializeSid, RtlInitializeSid routine [Installable File System Drivers], ifsk.rtlinitializesid, ntifs/RtlInitializeSid, rtlref_fbcc1ed7-4929-415f-9644-b8d9521a5c1a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: "< DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlInitializeSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlInitializeSid function


## -description


The <b>RtlInitializeSid</b> routine initializes a security identifier (SID) structure. 


## -syntax


````
NTSTATUS RtlInitializeSid(
  _Out_ PSID                      Sid,
  _In_  PSID_IDENTIFIER_AUTHORITY IdentifierAuthority,
  _In_  UCHAR                     SubAuthorityCount
);
````


## -parameters




### -param Sid [out]

Pointer to a caller-allocated SID structure to be initialized. 


### -param IdentifierAuthority [in]

Pointer to an SID_IDENTIFIER_AUTHORITY structure to set in the SID structure. 


### -param SubAuthorityCount [in]

Number of subauthorities to set in the SID. Subauthority values must be set separately, as described in the following Remarks section. 


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



Although <b>RtlInitializeSid</b> sets the number of subauthorities for the SID, it does not set the subauthority values. This must be done separately by calling <b>RtlSubAuthoritySid</b>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>



<a href="..\ntifs\ns-ntifs-_sid_identifier_authority.md">SID_IDENTIFIER_AUTHORITY</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeSid routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

