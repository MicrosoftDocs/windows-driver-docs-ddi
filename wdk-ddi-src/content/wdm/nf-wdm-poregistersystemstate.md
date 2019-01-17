---
UID: NF:wdm.PoRegisterSystemState
title: PoRegisterSystemState function
description: The PoRegisterSystemState routine registers the system as busy due to certain activity.
old-location: kernel\poregistersystemstate.htm
tech.root: kernel
ms.assetid: 851c694f-6c47-498c-8035-132a63c0fa62
ms.date: 04/30/2018
ms.keywords: PoRegisterSystemState, PoRegisterSystemState routine [Kernel-Mode Driver Architecture], kernel.poregistersystemstate, portn_477a2d72-00f7-45a1-b7ca-504b741c5fe0.xml, wdm/PoRegisterSystemState
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PoRegisterSystemState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoRegisterSystemState function


## -description


The <b>PoRegisterSystemState</b> routine registers the system as busy due to certain activity.


## -parameters




### -param StateHandle [in, out]

A pointer to a caller-supplied buffer for a registration state handle. The size, in bytes, of the buffer is <b>sizeof</b>(ULONG). If <b>NULL</b>, this is a new registration. If non-<b>NULL</b>, this parameter points to a handle that was returned by a previous call to <b>PoRegisterSystemState</b>.


### -param Flags [in]

Indicates the type of activity, as specified by a bitwise OR of one or more of the following values:





#### ES_SYSTEM_REQUIRED

The system is not idle, regardless of apparent load.



#### ES_DISPLAY_REQUIRED

Use of the display is required.



#### ES_USER_PRESENT

A user is present.



#### ES_CONTINUOUS

The settings are continuous and should remain in effect until explicitly changed.


##### - Flags.ES_CONTINUOUS

The settings are continuous and should remain in effect until explicitly changed.


##### - Flags.ES_DISPLAY_REQUIRED

Use of the display is required.


##### - Flags.ES_SYSTEM_REQUIRED

The system is not idle, regardless of apparent load.


##### - Flags.ES_USER_PRESENT

A user is present.


## -returns



<b>PoRegisterSystemState</b> returns a handle to be used later to change or unregister the system busy state. It returns <b>NULL</b> if the handle could not be allocated.




## -remarks



<b>PoRegisterSystemState</b> registers the system busy state as indicated by the flags. The registration persists until the caller explicitly changes it with another call to <b>PoRegisterSystemState</b> or cancels it with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a>.

The <i>Flags</i> parameter specifies the type of activity in progress. Drivers can specify any combination of the flags.

Setting ES_CONTINUOUS makes the busy state persist until a driver explicitly changes or cancels it by calling <b>PoRegisterSystemState</b> or <b>PoUnregisterSystemState</b>.

A driver can set the system busy state to request that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a> avoid system power state transitions out of the system working state (S0) while driver activity is occurring. Note, however, that under some circumstances (such as a critically low battery) the power manager may override this request and put the system to sleep anyway.

To set the system power state, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559768">PoSetSystemState</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff559768">PoSetSystemState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559794">PoUnregisterSystemState</a>
 

 

