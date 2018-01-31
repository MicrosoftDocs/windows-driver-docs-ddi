---
UID: NC:parallel.PPARALLEL_TRY_SELECT_ROUTINE
title: PPARALLEL_TRY_SELECT_ROUTINE
author: windows-driver-content
description: The PPARALLEL_TRY_SELECT_ROUTINE-typed callback routine selects an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. The system-supplied function driver for parallel ports supplies this routine.
old-location: parports\pparallel_try_select_routine.htm
old-project: parports
ms.assetid: e7ecc2ac-fb86-40fe-829b-ee5851c6ae5f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.pparallel_try_select_routine, (*PPARALLEL_TRY_SELECT_ROUTINE) callback function [Parallel Ports], (*PPARALLEL_TRY_SELECT_ROUTINE), parallel/(*PPARALLEL_TRY_SELECT_ROUTINE), cisspd_ec7d6b68-7fbd-493e-9787-3e2f78327bdd.xml
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
-	(*PPARALLEL_TRY_SELECT_ROUTINE)
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_TRY_SELECT_ROUTINE callback


## -description


The <i>PPARALLEL_TRY_SELECT_ROUTINE</i>-typed callback routine selects an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


````
typedef NTSTATUS (*PPARALLEL_TRY_SELECT_ROUTINE)(
  _In_ PVOID TrySelectContext,
  _In_ PVOID TrySelectCommand
);
````


## -parameters




#### - TrySelectContext [in]

Pointer to the device extension of a parallel port's functional device object (<a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>).


#### - TrySelectCommand [in]

Pointer to a <a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a> structure. The caller specifies the following members:




#### ID

Specifies the 1284.3 device ID. 


#### CommandFlags

Specifies a bitwise OR of zero or more of the following flags:
<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
PAR_END_OF_CHAIN_DEVICE

</td>
<td>
Specifies an end-of-chain device.

</td>
</tr>
<tr>
<td>
PAR_HAVE_PORT_KEEP_PORT

</td>
<td>
Specifies that the caller has the port allocated and to keep the port allocated.

</td>
</tr>
</table> 


## -returns


<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The device was selected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The device ID is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>
</td>
<td width="60%">
The caller did not specify PAR_HAVE_PORT_KEEP_PORT, and the parallel port is already allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The caller has allocated the parallel port, but the system-supplied function driver for parallel ports could not select the specified parallel device.

</td>
</tr>
</table> 



## -remarks


To obtain a pointer to the system-supplied <i>PPARALLEL_TRY_SELECT_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure. The <b>TrySelectDevice</b> member of the PARALLEL_PNP_INFORMATION structure is a pointer to this callback.

A kernel-mode driver can use an <a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a> request or the <i>PPARALLEL_TRY_SELECT_ROUTINE</i> callback to select a parallel device on a parallel port. The parallel port function driver queues a select request if the parallel port is already allocated. However, the <i>PPARALLEL_TRY_SELECT_ROUTINE</i> callback does not queue a select request, and the routine returns immediately if the port cannot be allocated.
<div class="alert"><b>Note</b>  
     If a client uses only the <i>PPARALLEL_TRY_SELECT_ROUTINE</i> callback to attempt to select a parallel device, and other clients are contending for the parallel port, the system-supplied function driver for parallel ports might never allocate the port to the client. To ensure success, a client must use an <a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a> request. (The parallel port function driver queues, and subsequently processes, port allocate requests and device select requests in the order in which select device requests are received.)</div><div> </div>For more information, see <a href="https://msdn.microsoft.com/1a3ac1b1-9180-4b71-8740-70c6fbe9a885">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.



## -see-also

<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>

<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>

<a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>

<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>

<a href="..\parallel\nc-parallel-pparallel_deselect_routine.md">PPARALLEL_DESELECT_ROUTINE</a>

<a href="..\parallel\ns-parallel-_parallel_1284_command.md">PARALLEL_1284_COMMAND</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_TRY_SELECT_ROUTINE callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

