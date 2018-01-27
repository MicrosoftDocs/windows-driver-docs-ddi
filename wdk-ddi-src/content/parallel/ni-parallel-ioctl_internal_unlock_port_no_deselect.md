---
UID: NI:parallel.IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
title: IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
author: windows-driver-content
description: The IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT request frees a parallel device's parent parallel port.
old-location: parports\ioctl_internal_unlock_port_no_deselect.htm
old-project: parports
ms.assetid: 516441bc-d240-43d2-a206-3d0bd8e712e9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.ioctl_internal_unlock_port_no_deselect, IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT control code [Parallel Ports], IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT, parallel/IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT, cisspd_a62d2a09-93e4-4fc4-ac5d-9589d930c794.xml
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
-	IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT
product: Windows
targetos: Windows
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
---

# IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


The <b>IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT</b> request frees a parallel device's parent parallel port. The request does not deselect the parallel device on the parallel port. 

This request is only supported in Windows XP and later.

For more information, see <a href="https://msdn.microsoft.com/dbfa962e-9de8-4a9c-b962-24b53c41f35d">Locking and Unlocking a ParallelPort for Use by a Parallel Device</a>.


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

The <b>Status</b> member is set to one of the generic status values returned by internal device control requests for parallel devices.


## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_lock_port_no_select.md">IOCTL_INTERNAL_LOCK_PORT_NO_SELECT</a>

<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>

<a href="..\parallel\ni-parallel-ioctl_internal_unlock_port.md">IOCTL_INTERNAL_UNLOCK_PORT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_INTERNAL_UNLOCK_PORT_NO_DESELECT control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

