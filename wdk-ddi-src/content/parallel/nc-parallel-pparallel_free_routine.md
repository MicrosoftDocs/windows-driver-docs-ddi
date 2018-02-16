---
UID: NC:parallel.PPARALLEL_FREE_ROUTINE
title: PPARALLEL_FREE_ROUTINE
author: windows-driver-content
description: The PPARALLEL_FREE_ROUTINE-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine.
old-location: parports\pparallel_free_routine.htm
old-project: parports
ms.assetid: 730872ee-3dfd-48c7-a86e-1a420e59471f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.pparallel_free_routine, (*PPARALLEL_FREE_ROUTINE) callback function [Parallel Ports], (*PPARALLEL_FREE_ROUTINE), parallel/(*PPARALLEL_FREE_ROUTINE), cisspd_5f5bcbed-0df6-4b2a-ab88-a26f48976ad7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	parallel.h
apiname:
-	(*PPARALLEL_FREE_ROUTINE)
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# PPARALLEL_FREE_ROUTINE callback


## -description


The <i>PPARALLEL_FREE_ROUTINE</i>-typed callback routine frees a parallel port. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


````
typedef VOID (*PPARALLEL_FREE_ROUTINE)(
  _In_ PVOID FreeContext
);
````


## -parameters




### -param FreeContext [in]

Pointer to the device extension of a parallel port's functional device object (<a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>).


## -returns



None




## -remarks



To obtain a pointer to the system-supplied <i>PPARALLEL_FREE_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a> structure. The <b>FreePort</b> member of the PARALLEL_PORT_INFORMATION structure is a pointer to this callback.

The driver should allocate a parallel port before freeing it. A driver can use <a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a> to determine the number of clients that are waiting to allocate the parallel port, and <a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a> to try to allocate the parallel port.

For more information, see <a href="https://msdn.microsoft.com/ea3a1998-9e31-4047-9193-6b402db222c9">Synchronizing the Use of a ParallelPort</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\nc-parallel-pparallel_try_allocate_routine.md">PPARALLEL_TRY_ALLOCATE_ROUTINE</a>



<a href="..\parallel\nc-parallel-pparallel_query_waiters_routine.md">PPARALLEL_QUERY_WAITERS_ROUTINE</a>



<a href="..\parallel\ns-parallel-_parallel_port_information.md">PARALLEL_PORT_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_FREE_ROUTINE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

