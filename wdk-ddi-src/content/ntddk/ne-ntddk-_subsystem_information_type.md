---
UID: NE:ntddk._SUBSYSTEM_INFORMATION_TYPE
title: "_SUBSYSTEM_INFORMATION_TYPE"
author: windows-driver-content
description: Indicates the type of subsystem for a process or thread. This enumeration is used in NtQueryInformationProcess and NtQueryInformationThread calls.
old-location: kernel\subsystem_information_type.htm
old-project: kernel
ms.assetid: B1E334BF-AAB3-410D-8D10-A750E8459E42
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PSUBSYSTEM_INFORMATION_TYPE, MaxSubsystemInformationType, SUBSYSTEM_INFORMATION_TYPE, SUBSYSTEM_INFORMATION_TYPE enumeration [Kernel-Mode Driver Architecture], SubsystemInformationTypeWSL, SubsystemInformationTypeWin32, _SUBSYSTEM_INFORMATION_TYPE, kernel.subsystem_information_type, ntddk/MaxSubsystemInformationType, ntddk/SUBSYSTEM_INFORMATION_TYPE, ntddk/SubsystemInformationTypeWSL, ntddk/SubsystemInformationTypeWin32"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	SUBSYSTEM_INFORMATION_TYPE
product: Windows
targetos: Windows
req.typenames: SUBSYSTEM_INFORMATION_TYPE, *PSUBSYSTEM_INFORMATION_TYPE
---

# _SUBSYSTEM_INFORMATION_TYPE enumeration


## -description


Indicates the type of subsystem for a process or thread. This enumeration is used in <a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a>  and <a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a> calls. 


## -enum-fields




### -field SubsystemInformationTypeWin32

The subsystem type for the process or thread is Win32.


### -field SubsystemInformationTypeWSL

The subsystem type for the process or thread is Windows Subsystem for Linux (WSL). For this process, these members of  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559960">PS_CREATE_NOTIFY_INFO</a> structure are set as follows:

<ul>
<li>The <b>FileObject</b> member is the NTFS file object from LxFs or DriveFs, the file system that is used for interoperability with Windows. </li>
<li>The <b>ImageFileName</b> member is the Linux path of the image file. </li>
<li>The <b>CommandLine</b> member is the Linux NULL-separated command line. </li>
</ul>
 The preceding member values may be NULL.


### -field MaxSubsystemInformationType

Reserved.


## -see-also




<a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a>



<a href="https://msdn.microsoft.com/ca292efc-1ea9-4c0f-b0a7-1cfb35d69f81">NtQueryInformationThread</a>
 

 

