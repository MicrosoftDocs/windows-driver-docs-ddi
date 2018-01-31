---
UID: NF:ntddk.PsGetProcessId
title: PsGetProcessId function
author: windows-driver-content
description: The PsGetProcessId routine returns the process identifier (process ID) that is associated with a specified process.
old-location: kernel\psgetprocessid.htm
old-project: kernel
ms.assetid: 9e1f6a57-bc48-41c6-815c-6a44e8d01699
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.psgetprocessid, PsGetProcessId, PsGetProcessId routine [Kernel-Mode Driver Architecture], k108_b0733011-4102-4e10-83e3-e7e9d7172d08.xml, ntddk/PsGetProcessId
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PsGetProcessId
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetProcessId function


## -description


The <b>PsGetProcessId</b> routine returns the process identifier (process ID) that is associated with a specified process. 


## -syntax


````
HANDLE PsGetProcessId(
  _In_ PEPROCESS Process
);
````


## -parameters




#### - Process [in]

A pointer to a process object structure. 


## -returns


<b>PsGetProcessId</b> returns the process ID of the process that the <i>Process</i> parameter specifies.



## -remarks


The EPROCESS-typed process object structure is an opaque data structure that the operating system uses internally. To obtain a pointer to the EPROCESS structure for the current process, a driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>. To obtain a pointer to the EPROCESS structure for a different process, the driver can call <a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>

<a href="..\wdm\nf-wdm-obreferenceobjectbyhandle.md">ObReferenceObjectByHandle</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PsGetProcessId routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

