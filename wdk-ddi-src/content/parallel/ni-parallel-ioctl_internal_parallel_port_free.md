---
UID: NI:parallel.IOCTL_INTERNAL_PARALLEL_PORT_FREE
title: IOCTL_INTERNAL_PARALLEL_PORT_FREE
author: windows-driver-content
description: The IOCTL_INTERNAL_PARALLEL_PORT_FREE request frees a parallel port.
old-location: parports\ioctl_internal_parallel_port_free.htm
old-project: parports
ms.assetid: bdf44009-4898-4890-9441-918e1647566d
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: parports.ioctl_internal_parallel_port_free, IOCTL_INTERNAL_PARALLEL_PORT_FREE control code [Parallel Ports], IOCTL_INTERNAL_PARALLEL_PORT_FREE, parallel/IOCTL_INTERNAL_PARALLEL_PORT_FREE, cisspd_ec1947dc-7124-445b-8b4a-759d6cba8225.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: parallel.h
req.include-header: Parallel.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	parallel.h
apiname:
-	IOCTL_INTERNAL_PARALLEL_PORT_FREE
product: Windows
targetos: Windows
req.typenames: "*LPRILGBATOKEN, RILGBATOKEN"
---

# IOCTL_INTERNAL_PARALLEL_PORT_FREE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request frees a parallel port. After using a parallel port, a client must free it. Microsoft recommends using the system-supplied <a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a> callback to free a parallel port because there is no functional advantage to using an <b>IOCTL_INTERNAL_PARALLEL_PORT_FREE</b> request to free the port.

For more information, see <a href="https://msdn.microsoft.com/ea3a1998-9e31-4047-9193-6b402db222c9">Synchronizing the Use of a ParallelPort</a>.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel ports.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_port_allocate.md">IOCTL_INTERNAL_PARALLEL_PORT_ALLOCATE</a>



<a href="..\parallel\nc-parallel-pparallel_free_routine.md">PPARALLEL_FREE_ROUTINE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_PARALLEL_PORT_FREE control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

