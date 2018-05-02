---
UID: NF:ntddk.PsGetProcessId
title: PsGetProcessId function
author: windows-driver-content
description: The PsGetProcessId routine returns the process identifier (process ID) that is associated with a specified process.
old-location: kernel\psgetprocessid.htm
old-project: kernel
ms.assetid: 9e1f6a57-bc48-41c6-815c-6a44e8d01699
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PsGetProcessId, PsGetProcessId routine [Kernel-Mode Driver Architecture], k108_b0733011-4102-4e10-83e3-e7e9d7172d08.xml, kernel.psgetprocessid, ntddk/PsGetProcessId
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	PsGetProcessId
product: Windows
targetos: Windows
req.typenames: 
---

# PsGetProcessId function


## -description


The <b>PsGetProcessId</b> routine returns the process identifier (process ID) that is associated with a specified process. 


## -parameters




### -param Process [in]

A pointer to a process object structure. 


## -returns



<b>PsGetProcessId</b> returns the process ID of the process that the <i>Process</i> parameter specifies.




## -remarks



The EPROCESS-typed process object structure is an opaque data structure that the operating system uses internally. To obtain a pointer to the EPROCESS structure for the current process, a driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>. To obtain a pointer to the EPROCESS structure for a different process, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558679">ObReferenceObjectByHandle</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>
 

 

