---
UID: NF:ntifs.RtlGetAce
title: RtlGetAce function
author: windows-driver-content
description: The RtlGetAce routine obtains a pointer to an access control entry (ACE) in an access control list (ACL).
old-location: ifsk\rtlgetace.htm
old-project: ifsk
ms.assetid: f528d20a-16f8-401f-a6e6-ab165a40e18a
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: ntifs/RtlGetAce, RtlGetAce, RtlGetAce routine [Installable File System Drivers], ifsk.rtlgetace, rtlref_e018acc3-f776-4d15-9e0b-9e34d286a746.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows XP and later.
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
-	RtlGetAce
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# RtlGetAce function


## -description


The <b>RtlGetAce</b> routine obtains a pointer to an access control entry (ACE) in an access control list (ACL). 


## -syntax


````
NTSTATUS RtlGetAce(
  _In_  PACL  Acl,
  _In_  ULONG AceIndex,
  _Out_ PVOID *Ace
);
````


## -parameters




### -param Acl [in]

Pointer to an ACL containing the ACE to be retrieved. 


### -param AceIndex [in]

Specifies the ACE to which a pointer is retrieved. A value of zero corresponds to the first ACE in the ACL, 1 to the second ACE, and so on. 


### -param Ace [out]

Pointer to a caller-allocated variable to receive the address of the ACE within the ACL. 


## -returns



<b>RtlGetAce</b> returns STATUS_SUCCESS or an error status code such as STATUS_INVALID_PARAMETER. 




## -remarks



For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\ntifs\nf-ntifs-rtlcreateacl.md">RtlCreateAcl</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff538844">ACE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGetAce routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

