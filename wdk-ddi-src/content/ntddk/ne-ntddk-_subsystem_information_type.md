---
UID: NE:ntddk._SUBSYSTEM_INFORMATION_TYPE
title: _SUBSYSTEM_INFORMATION_TYPE (ntddk.h)
description: Indicates the type of subsystem for a process or thread. This enumeration is used in NtQueryInformationProcess and NtQueryInformationThread calls.
old-location: kernel\subsystem_information_type.htm
tech.root: kernel
ms.assetid: B1E334BF-AAB3-410D-8D10-A750E8459E42
ms.date: 04/30/2018
keywords: ["SUBSYSTEM_INFORMATION_TYPE enumeration"]
ms.keywords: "*PSUBSYSTEM_INFORMATION_TYPE, MaxSubsystemInformationType, SUBSYSTEM_INFORMATION_TYPE, SUBSYSTEM_INFORMATION_TYPE enumeration [Kernel-Mode Driver Architecture], SubsystemInformationTypeWSL, SubsystemInformationTypeWin32, _SUBSYSTEM_INFORMATION_TYPE, kernel.subsystem_information_type, ntddk/MaxSubsystemInformationType, ntddk/SUBSYSTEM_INFORMATION_TYPE, ntddk/SubsystemInformationTypeWSL, ntddk/SubsystemInformationTypeWin32"
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE
f1_keywords:
 - _SUBSYSTEM_INFORMATION_TYPE
 - ntddk/_SUBSYSTEM_INFORMATION_TYPE
 - PSUBSYSTEM_INFORMATION_TYPE
 - ntddk/PSUBSYSTEM_INFORMATION_TYPE
 - SUBSYSTEM_INFORMATION_TYPE
 - ntddk/SUBSYSTEM_INFORMATION_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - SUBSYSTEM_INFORMATION_TYPE
---

# _SUBSYSTEM_INFORMATION_TYPE enumeration


## -description

Indicates the type of subsystem for a process or thread. This enumeration is used in <a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationprocess">NtQueryInformationProcess</a>  and <a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationthread">NtQueryInformationThread</a> calls.

## -enum-fields

### -field SubsystemInformationTypeWin32

The subsystem type for the process or thread is Win32.

### -field SubsystemInformationTypeWSL

The subsystem type for the process or thread is Windows Subsystem for Linux (WSL). For this process, these members of  the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_ps_create_notify_info">PS_CREATE_NOTIFY_INFO</a> structure are set as follows:

<ul>
<li>The <b>FileObject</b> member is the NTFS file object from LxFs or DriveFs, the file system that is used for interoperability with Windows. </li>
<li>The <b>ImageFileName</b> member is the Linux path of the image file. </li>
<li>The <b>CommandLine</b> member is the Linux NULL-separated command line. </li>
</ul>
 The preceding member values may be NULL.

### -field MaxSubsystemInformationType

Reserved.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationprocess">NtQueryInformationProcess</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationthread">NtQueryInformationThread</a>

