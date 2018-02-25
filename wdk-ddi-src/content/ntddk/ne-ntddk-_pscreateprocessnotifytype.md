---
UID: NE:ntddk._PSCREATEPROCESSNOTIFYTYPE
title: "_PSCREATEPROCESSNOTIFYTYPE"
author: windows-driver-content
description: Indicates the type of process notification. This enumeration is used in PsSetCreateProcessNotifyRoutineEx2 to register callback notifications.
old-location: kernel\pscreateprocessnotifytype.htm
old-project: kernel
ms.assetid: 5DD02CF1-50E8-45F2-9035-E0AA48F1470C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , ,, A, C, E, F, I, N, O, P, PSCREATEPROCESSNOTIFYTYPE, PSCREATEPROCESSNOTIFYTYPE enumeration [Kernel-Mode Driver Architecture], PsCreateProcessNotifySubsystems, R, S, T, Y, _, _PSCREATEPROCESSNOTIFYTYPE, kernel.pscreateprocessnotifytype, ntddk/PSCREATEPROCESSNOTIFYTYPE, ntddk/PsCreateProcessNotifySubsystems"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddk.h
apiname:
-	PSCREATEPROCESSNOTIFYTYPE
product: Windows
targetos: Windows
req.typenames: PSCREATEPROCESSNOTIFYTYPE
---

# _PSCREATEPROCESSNOTIFYTYPE enumeration


## -description


Indicates the type of process notification. This enumeration is used in <a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutineex2.md">PsSetCreateProcessNotifyRoutineEx2</a> to register callback notifications.


## -syntax


````
typedef enum _PSCREATEPROCESSNOTIFYTYPE { 
  PsCreateProcessNotifySubsystems  = 0
} PSCREATEPROCESSNOTIFYTYPE;
````


## -enum-fields




### -field PsCreateProcessNotifySubsystems

Indicates that the driver-registered callback is invoked for processes of all subsystems, including the Win32 subsystem. Drivers can call <a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a> to determine the underlying subsystem. The query retrieves a  <a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a> value.


## -see-also

<a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutineex2.md">PsSetCreateProcessNotifyRoutineEx2</a>



<a href="https://msdn.microsoft.com/0eae7899-c40b-4a5f-9e9c-adae021885e7">NtQueryInformationProcess</a>



<a href="..\ntddk\ne-ntddk-_subsystem_information_type.md">SUBSYSTEM_INFORMATION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PSCREATEPROCESSNOTIFYTYPE enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

