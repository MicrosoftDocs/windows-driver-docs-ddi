---
UID: NF:ntifs.PsReferencePrimaryToken
title: PsReferencePrimaryToken function
author: windows-driver-content
description: The PsReferencePrimaryToken routine increments the reference count of the primary token for the specified process.
old-location: ifsk\psreferenceprimarytoken.htm
old-project: ifsk
ms.assetid: 8ff1add9-4b9e-42dd-b3e2-53d891788d43
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , P, PsReferencePrimaryToken, PsReferencePrimaryToken routine [Installable File System Drivers], R, T, a, c, e, f, i, ifsk.psreferenceprimarytoken, k, m, n, ntifs/PsReferencePrimaryToken, o, psref_021aea60-1707-4817-9169-95a3dc79adb6.xml, r, s, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsReferencePrimaryToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---

# PsReferencePrimaryToken function


## -description


The <b>PsReferencePrimaryToken</b> routine increments the reference count of the primary token for the specified process.


## -syntax


````
PACCESS_TOKEN PsReferencePrimaryToken(
  _Inout_ PEPROCESS Process
);
````


## -parameters




### -param Process [in, out]

Pointer to the process whose primary token's reference count is to be incremented.


## -returns



<b>PsReferencePrimaryToken</b> returns a pointer to the primary token for the given process. 




## -remarks



This routine is available starting with Microsoft Windows 2000. 

<b>PsReferencePrimaryToken</b> increments the reference count of the returned primary token. Thus for every successful call to <b>PsReferencePrimaryToken</b>, the primary token's reference count must be decremented by calling one of the following functions:

<ul>
<li>
<b>ObDereferenceObject</b>, for Windows 2000

</li>
<li>
<b>PsDereferencePrimaryToken</b>, for Microsoft Windows XP and later.

</li>
</ul>
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK. 




## -see-also

<a href="..\wdm\nf-wdm-obdereferenceobject.md">ObDereferenceObject</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-psreferenceimpersonationtoken.md">PsReferenceImpersonationToken</a>



<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20PsReferencePrimaryToken routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

