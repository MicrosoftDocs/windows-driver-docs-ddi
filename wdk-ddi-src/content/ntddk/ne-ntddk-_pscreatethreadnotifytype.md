---
UID: NE:ntddk._PSCREATETHREADNOTIFYTYPE
title: _PSCREATETHREADNOTIFYTYPE (ntddk.h)
description: Indicates the type of thread notification. This enumeration is used in PsSetCreateThreadNotifyRoutineEx to register callback notifications associated with thread creation or deletion.
old-location: kernel\pscreatethreadnotifytype.htm
tech.root: kernel
ms.assetid: C38F8222-7F22-4D6B-A3F2-C326ECE22E8B
ms.date: 04/30/2018
keywords: ["PSCREATETHREADNOTIFYTYPE enumeration"]
ms.keywords: PSCREATETHREADNOTIFYTYPE, PSCREATETHREADNOTIFYTYPE enumeration [Kernel-Mode Driver Architecture], PsCreateThreadNotifyNonSystem, PsCreateThreadNotifySubsystems, _PSCREATETHREADNOTIFYTYPE, kernel.pscreatethreadnotifytype, ntddk/PSCREATETHREADNOTIFYTYPE, ntddk/PsCreateThreadNotifyNonSystem, ntddk/PsCreateThreadNotifySubsystems
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1703
req.target-min-winversvr: Windows Server 2016
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
req.typenames: PSCREATETHREADNOTIFYTYPE
f1_keywords:
 - _PSCREATETHREADNOTIFYTYPE
 - ntddk/_PSCREATETHREADNOTIFYTYPE
 - PSCREATETHREADNOTIFYTYPE
 - ntddk/PSCREATETHREADNOTIFYTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - PSCREATETHREADNOTIFYTYPE
---

# _PSCREATETHREADNOTIFYTYPE enumeration


## -description

Indicates the type of thread notification. This enumeration is used in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutineex">PsSetCreateThreadNotifyRoutineEx</a> to register callback notifications associated with thread creation or deletion.

## -enum-fields

### -field PsCreateThreadNotifyNonSystem

The driver-registered callback function is executed on the new non-system thread, which enables the callback function to perform tasks such as setting the initial thread context.

### -field PsCreateThreadNotifySubsystems

Indicates that the driver-registered callback function is invoked for threads of all subsystems.  Drivers can call <a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationthread">NtQueryInformationThread</a> to determine the underlying subsystem. The query retrieves a  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_subsystem_information_type">SUBSYSTEM_INFORMATION_TYPE</a> value.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/winternl/nf-winternl-ntqueryinformationthread">NtQueryInformationThread</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreatethreadnotifyroutineex">PsSetCreateThreadNotifyRoutineEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_subsystem_information_type">SUBSYSTEM_INFORMATION_TYPE</a>

