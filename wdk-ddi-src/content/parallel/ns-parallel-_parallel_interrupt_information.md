---
UID: NS:parallel._PARALLEL_INTERRUPT_INFORMATION
title: _PARALLEL_INTERRUPT_INFORMATION
author: windows-driver-content
description: The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port.
old-location: parports\parallel_interrupt_information.htm
old-project: parports
ms.assetid: aa4baa12-c349-4961-9694-b8fb3cd8dc50
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _PARALLEL_INTERRUPT_INFORMATION, *PPARALLEL_INTERRUPT_INFORMATION, PARALLEL_INTERRUPT_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PARALLEL_INTERRUPT_INFORMATION
req.alt-loc: parallel.h
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
req.typenames: *PPARALLEL_INTERRUPT_INFORMATION, PARALLEL_INTERRUPT_INFORMATION
---

# _PARALLEL_INTERRUPT_INFORMATION structure



## -description
The PARALLEL_INTERRUPT_INFORMATION structure specifies information that a kernel-mode driver can use in the context of an ISR that the driver connects to a parallel port.



## -syntax

````
typedef struct _PARALLEL_INTERRUPT_INFORMATION {
  PKINTERRUPT                    InterruptObject;
  PPARALLEL_TRY_ALLOCATE_ROUTINE TryAllocatePortAtInterruptLevel;
  PPARALLEL_FREE_ROUTINE         FreePortFromInterruptLevel;
  PVOID                          Context;
} PARALLEL_INTERRUPT_INFORMATION, *PPARALLEL_INTERRUPT_INFORMATION;
````


## -struct-fields

### -field InterruptObject

Pointer to the parallel port interrupt object.


### -field TryAllocatePortAtInterruptLevel

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE (ISR)</a> callback routine that a kernel-mode driver can use to attempt to allocate the parallel port at IRQL = DIRQL.


### -field FreePortFromInterruptLevel

Pointer to the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE (ISR)</a> callback routine that a kernel-mode driver can use to free the parallel port at IRQL = DIRQL.


### -field Context

Pointer to the device extension of a functional device object that represents the parallel port.


## -remarks
A kernel-mode driver can use the parallel interrupt information in the context of an interrupt service routine (ISR). A driver connects an ISR using an <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request.


## -see-also
<dl>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>
</dt>
<dt>
<a href="..\parallel\ni-parallel-ioctl_internal_parallel_disconnect_interrupt.md">IOCTL_INTERNAL_PARALLEL_DISCONNECT_INTERRUPT</a>
</dt>
<dt>
<a href="..\parallel\ns-parallel-_parallel_interrupt_service_routine.md">PARALLEL_INTERRUPT_SERVICE_ROUTINE</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE (ISR)</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE (ISR)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PARALLEL_INTERRUPT_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

