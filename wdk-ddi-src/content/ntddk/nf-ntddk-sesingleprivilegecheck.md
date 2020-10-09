---
UID: NF:ntddk.SeSinglePrivilegeCheck
title: SeSinglePrivilegeCheck function (ntddk.h)
description: The SeSinglePrivilegeCheck routine checks for the passed privilege value in the context of the current thread.
old-location: kernel\sesingleprivilegecheck.htm
tech.root: kernel
ms.assetid: bb83318c-b14f-421a-9cd4-69e270b825c7
ms.date: 04/30/2018
keywords: ["SeSinglePrivilegeCheck function"]
ms.keywords: SeSinglePrivilegeCheck, SeSinglePrivilegeCheck routine [Kernel-Mode Driver Architecture], k110_ee767278-7c5f-4dcd-b328-e9219b453a84.xml, kernel.sesingleprivilegecheck, ntddk/SeSinglePrivilegeCheck
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
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
 - SeSinglePrivilegeCheck
 - ntddk/SeSinglePrivilegeCheck
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - SeSinglePrivilegeCheck
---

# SeSinglePrivilegeCheck function


## -description

The 
   <b>SeSinglePrivilegeCheck</b> routine checks for the passed privilege value in the context of the current thread.

## -parameters

### -param PrivilegeValue 

[in]
Specifies the <a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a> value of the privilege being checked.

### -param PreviousMode 

[in]
Specifies the previous execution mode, one of <b>UserMode</b> or <b>KernelMode</b>.

## -returns

<b>SeSinglePrivilegeCheck</b> returns <b>TRUE</b> if the current subject has the required privilege.

## -remarks

If <i>PreviousMode</i> is <b>KernelMode</b>, the privilege check always succeeds. Otherwise, this routine uses the token of the user-mode thread to determine whether the current (user-mode) thread has been granted the given privilege.

## -see-also

<a href="/windows-hardware/drivers/ddi/igpupvdev/ns-igpupvdev-_luid">LUID</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlconvertlongtoluid">RtlConvertLongToLuid</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-rtlconvertulongtoluid">RtlConvertUlongToLuid</a>



<a href="/windows-hardware/drivers/kernel/mm-bad-pointer">RtlEqualLuid</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-sevalidsecuritydescriptor">SeValidSecurityDescriptor</a>