---
UID: NF:ntifs.PsReferencePrimaryToken
title: PsReferencePrimaryToken function (ntifs.h)
description: The PsReferencePrimaryToken routine increments the reference count of the primary token for the specified process.
old-location: ifsk\psreferenceprimarytoken.htm
tech.root: ifsk
ms.assetid: 8ff1add9-4b9e-42dd-b3e2-53d891788d43
ms.date: 04/16/2018
keywords: ["PsReferencePrimaryToken function"]
ms.keywords: PsReferencePrimaryToken, PsReferencePrimaryToken routine [Installable File System Drivers], ifsk.psreferenceprimarytoken, ntifs/PsReferencePrimaryToken, psref_021aea60-1707-4817-9169-95a3dc79adb6.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsReferencePrimaryToken
 - ntifs/PsReferencePrimaryToken
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsReferencePrimaryToken
---

# PsReferencePrimaryToken function


## -description

The <b>PsReferencePrimaryToken</b> routine increments the reference count of the primary token for the specified process.

## -parameters

### -param Process 

[in, out]
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-obdereferenceobject">ObDereferenceObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psdereferenceprimarytoken">PsDereferencePrimaryToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psreferenceimpersonationtoken">PsReferenceImpersonationToken</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-sequeryinformationtoken">SeQueryInformationToken</a>

