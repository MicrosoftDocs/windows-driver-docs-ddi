---
UID: NE:ntddk._PSCREATEPROCESSNOTIFYTYPE
title: "_PSCREATEPROCESSNOTIFYTYPE"
author: windows-driver-content
description: Indicates the type of process notification. This enumeration is used in PsSetCreateProcessNotifyRoutineEx2 to register callback notifications.
old-location: kernel\pscreateprocessnotifytype.htm
old-project: kernel
ms.assetid: 5DD02CF1-50E8-45F2-9035-E0AA48F1470C
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PSCREATEPROCESSNOTIFYTYPE, PSCREATEPROCESSNOTIFYTYPE enumeration [Kernel-Mode Driver Architecture], PsCreateProcessNotifySubsystems, _PSCREATEPROCESSNOTIFYTYPE, kernel.pscreateprocessnotifytype, ntddk/PSCREATEPROCESSNOTIFYTYPE, ntddk/PsCreateProcessNotifySubsystems
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	PSCREATEPROCESSNOTIFYTYPE
product:
- Windows
targetos: Windows
req.typenames: PSCREATEPROCESSNOTIFYTYPE
---

# _PSCREATEPROCESSNOTIFYTYPE enumeration


## -description


Indicates the type of process notification. This enumeration is used in <a href="https://msdn.microsoft.com/library/windows/hardware/mt805891">PsSetCreateProcessNotifyRoutineEx2</a> to register callback notifications.


## -enum-fields




### -field PsCreateProcessNotifySubsystems

Indicates that the driver-registered callback is invoked for processes of all subsystems, including the Win32 subsystem. Drivers can call <a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a> to determine the underlying subsystem. The query retrieves a  <a href="https://msdn.microsoft.com/library/windows/hardware/mt805892">SUBSYSTEM_INFORMATION_TYPE</a> value.


## -see-also




<a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt805891">PsSetCreateProcessNotifyRoutineEx2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt805892">SUBSYSTEM_INFORMATION_TYPE</a>
 

 

