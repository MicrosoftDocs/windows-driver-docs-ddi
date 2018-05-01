---
UID: NF:wdm.PoSetSystemState
title: PoSetSystemState function
author: windows-driver-content
description: Drivers call the PoSetSystemState routine to indicate that the system is active.
old-location: kernel\posetsystemstate.htm
old-project: kernel
ms.assetid: b62db582-381a-457f-9755-d8667c7561af
ms.author: windowsdriverdev
ms.date: 4/5/2018
ms.keywords: PoSetSystemState, PoSetSystemState routine [Kernel-Mode Driver Architecture], kernel.posetsystemstate, portn_f20a5d5b-d863-4ff7-8837-6a7e625271d7.xml, wdm/PoSetSystemState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoSetSystemState
product: Windows
targetos: Windows
req.typenames: 
---

# PoSetSystemState function


## -description


Drivers call the <b>PoSetSystemState</b> routine to indicate that the system is active.


## -parameters




### -param Flags [in]

Indicates the system activity, as specified by a bitwise OR of one or more of the following values:





#### ES_SYSTEM_REQUIRED

The system is not idle, regardless of apparent load.



#### ES_DISPLAY_REQUIRED

Use of the display is required.



#### ES_USER_PRESENT

A user is present.


## -returns



None




## -remarks



A driver calls <b>PoSetSystemState</b> to set flags indicating that system activity is occurring. Unlike <a href="https://msdn.microsoft.com/library/windows/hardware/ff559731">PoRegisterSystemState</a>, this routine does not allow the driver to set a persistent busy state. 

The <i>Flags</i> parameter specifies the type of activity occurring. Drivers can specify any combination of the flags.

Drivers can set the system busy state to request that the system avoid leaving of the working state while driver activity is occurring. Note, however, that under some circumstances (such as a critically low battery) the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> may override this request and put the system to sleep anyway. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559731">PoRegisterSystemState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a>
 

 

