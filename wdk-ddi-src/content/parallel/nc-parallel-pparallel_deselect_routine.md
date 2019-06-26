---
UID: NC:parallel.PPARALLEL_DESELECT_ROUTINE
title: PPARALLEL_DESELECT_ROUTINE (parallel.h)
description: The PPARALLEL_DESELECT_ROUTINE-typed callback routine deselects either an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port.
old-location: parports\pparallel_deselect_routine.htm
tech.root: parports
ms.assetid: 91182ed5-e444-41a7-b6fc-f14d0407f089
ms.date: 02/15/2018
ms.keywords: "(*PPARALLEL_DESELECT_ROUTINE), (*PPARALLEL_DESELECT_ROUTINE) callback function [Parallel Ports], cisspd_e8bc6fa2-03e4-4845-bfd6-0ebaf573e1b2.xml, parallel/(*PPARALLEL_DESELECT_ROUTINE), parports.pparallel_deselect_routine"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- parallel.h
api_name:
- (*PPARALLEL_DESELECT_ROUTINE)
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_DESELECT_ROUTINE callback


## -description


The <i>PPARALLEL_DESELECT_ROUTINE</i>-typed callback routine deselects either an IEEE 1284.3 daisy chain device or an IEEE 1284 end-of-chain device that is attached to a parallel port. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef NTSTATUS (*PPARALLEL_DESELECT_ROUTINE)(
  _In_ PVOID DeselectContext,
  _In_ PVOID DeselectCommand
);
```


## -parameters




### -param DeselectContext [in]

Pointer to the device extension of a functional device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">FDO</a>) that represents a parallel port.


### -param DeselectCommand [in]

Pointer to a PARALLEL_1284_COMMAND structure. The caller specifies the following members:





#### ID

Specifies the 1284.3 device ID (zero or 1).



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
Specifies that the port be kept allocated.

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
The device was deselected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified device ID is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The system-supplied function driver for parallel ports could not deselect the device.

</td>
</tr>
</table>
 




## -remarks



To obtain a pointer to the system-supplied <i>PPARALLEL_DESELECT_ROUTINE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure. The <b>DeselectDevice</b> member of the PARALLEL_PNP_INFORMATION structure is a pointer to this callback.

A kernel-mode driver can use an <a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a> request or the <i>PPARALLEL_CLEAR_CHIP_MODE</i> callback to deselect a device on a parallel port represented by a parallel port. To deselect a device, a caller should have the parallel port allocated. If the caller does not set the PAR_HAVE_PORT_KEEP_PORT flag, the system-supplied function driver for parallel ports frees the parallel port after deselecting the device.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff544793(v=vs.85)">Selecting and Deselecting an IEEE 1284 Device Attached to a ParallelPort</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_select_device.md">IOCTL_INTERNAL_SELECT_DEVICE</a>



<a href="..\parallel\nc-parallel-pparallel_try_select_routine.md">PPARALLEL_TRY_SELECT_ROUTINE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_deselect_device.md">IOCTL_INTERNAL_DESELECT_DEVICE</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



 

 


