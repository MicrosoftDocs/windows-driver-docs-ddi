---
UID: NF:wdm.MmGetSystemRoutineAddress
title: MmGetSystemRoutineAddress function
author: windows-driver-content
description: The MmGetSystemRoutineAddress routine returns a pointer to a function specified by SystemRoutineName.
old-location: kernel\mmgetsystemroutineaddress.htm
old-project: kernel
ms.assetid: 87e20abc-eb65-40c0-943e-eb194022a2de
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k106_4cd56243-e8f4-428a-95f2-4e7a1d2a7396.xml, wdm/MmGetSystemRoutineAddress, MmGetSystemRoutineAddress, kernel.mmgetsystemroutineaddress, MmGetSystemRoutineAddress routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmGetSystemRoutineAddress
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmGetSystemRoutineAddress function


## -description


The <b>MmGetSystemRoutineAddress</b> routine returns a pointer to a function specified by <i>SystemRoutineName</i>. 


## -syntax


````
PVOID MmGetSystemRoutineAddress(
  _In_ PUNICODE_STRING SystemRoutineName
);
````


## -parameters




#### - SystemRoutineName [in]

Specifies the name of the system routine to resolve. 


## -returns


If the function name can be resolved, the routine returns a pointer to the function. Otherwise, the routine returns <b>NULL</b>.



## -remarks


Drivers can use this routine to determine if a routine is available on a specific version of Windows. It can only be used for routines exported by the kernel or HAL, not for any driver-defined routine. 



## -see-also

<a href="..\wdm\nf-wdm-ioiswdmversionavailable.md">IoIsWdmVersionAvailable</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmGetSystemRoutineAddress routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

