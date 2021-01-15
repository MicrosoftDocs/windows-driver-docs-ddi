---
UID: NE:ntddk._PSCREATEPROCESSNOTIFYTYPE
title: _PSCREATEPROCESSNOTIFYTYPE (ntddk.h)
description: Indicates the type of process notification. This enumeration is used in PsSetCreateProcessNotifyRoutineEx2 to register callback notifications.
old-location: kernel\pscreateprocessnotifytype.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PSCREATEPROCESSNOTIFYTYPE enumeration"]
ms.keywords: PSCREATEPROCESSNOTIFYTYPE, PSCREATEPROCESSNOTIFYTYPE enumeration [Kernel-Mode Driver Architecture], PsCreateProcessNotifySubsystems, _PSCREATEPROCESSNOTIFYTYPE, kernel.pscreateprocessnotifytype, ntddk/PSCREATEPROCESSNOTIFYTYPE, ntddk/PsCreateProcessNotifySubsystems
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
req.typenames: PSCREATEPROCESSNOTIFYTYPE
f1_keywords:
 - _PSCREATEPROCESSNOTIFYTYPE
 - ntddk/_PSCREATEPROCESSNOTIFYTYPE
 - PSCREATEPROCESSNOTIFYTYPE
 - ntddk/PSCREATEPROCESSNOTIFYTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddk.h
api_name:
 - _PSCREATEPROCESSNOTIFYTYPE
 - PSCREATEPROCESSNOTIFYTYPE
---

# _PSCREATEPROCESSNOTIFYTYPE enumeration


## -description

Indicates the type of process notification. This enumeration is used in <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex2">PsSetCreateProcessNotifyRoutineEx2</a> to register callback notifications.

## -enum-fields

### -field PsCreateProcessNotifySubsystems

Indicates that the driver-registered callback is invoked for processes of all subsystems, including the Win32 subsystem. Drivers can call <a href="/windows/win32/api/winternl/nf-winternl-ntqueryinformationprocess">NtQueryInformationProcess</a> to determine the underlying subsystem. The query retrieves a  <a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_subsystem_information_type">SUBSYSTEM_INFORMATION_TYPE</a> value.

## -see-also

<a href="/windows/win32/api/winternl/nf-winternl-ntqueryinformationprocess">NtQueryInformationProcess</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-pssetcreateprocessnotifyroutineex2">PsSetCreateProcessNotifyRoutineEx2</a>



<a href="/windows-hardware/drivers/ddi/ntddk/ne-ntddk-_subsystem_information_type">SUBSYSTEM_INFORMATION_TYPE</a>

