---
UID: NC:parallel.PPARALLEL_CLEAR_CHIP_MODE
title: PPARALLEL_CLEAR_CHIP_MODE
author: windows-driver-content
description: The PPARALLEL_CLEAR_CHIP_MODE-typed callback routine clears the operating mode of a parallel port by resetting the communication mode of the host chipset to IEEE 1284-compatibility mode.
old-location: parports\pparallel_clear_chip_mode.htm
tech.root: parports
ms.assetid: 398d38a0-2337-4f8e-bd30-d6546516b945
ms.date: 02/15/2018
ms.keywords: "(*PPARALLEL_CLEAR_CHIP_MODE), (*PPARALLEL_CLEAR_CHIP_MODE) callback function [Parallel Ports], cisspd_d5564f9d-0941-4f80-9fa7-5acacaaf47a9.xml, parallel/(*PPARALLEL_CLEAR_CHIP_MODE), parports.pparallel_clear_chip_mode"
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	parallel.h
api_name:
-	(*PPARALLEL_CLEAR_CHIP_MODE)
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_CLEAR_CHIP_MODE callback


## -description


The <i>PPARALLEL_CLEAR_CHIP_MODE</i>-typed callback routine clears the operating mode of a parallel port by resetting the communication mode of the host chipset to IEEE 1284-compatibility mode. The system-supplied function driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef NTSTATUS (*PPARALLEL_CLEAR_CHIP_MODE)(
  _In_ PVOID ClearChipContext,
  _In_ UCHAR ChipMode
);
```


## -parameters




### -param ClearChipContext [in]

Pointer to the device extension of a parallel port's functional device object (<a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">FDO</a>).


### -param ChipMode [in]

Specifies the current operating mode of the parallel port.

For more information about operating modes, see the modes that are defined for the enhanced capabilities register (ECR) in the <i>parallel.h</i> file that is included in the Microsoft Windows Driver Kit (WDK).


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
The operating mode was set to IEEE 1284-compatibility mode.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The specified mode does not match the current mode.

</td>
</tr>
</table>
 




## -remarks



To obtain a pointer to the system-supplied <i>PPARALLEL_CLEAR_CHIP_MODE</i> callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_pnp_info.md">IOCTL_INTERNAL_GET_PARALLEL_PNP_INFO</a> request, which returns a <a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a> structure. The <b>ClearChipMode</b> member of the PARALLEL_PNP_INFORMATION structure is a pointer to this callback.

A caller uses the <i>PPARALLEL_CLEAR_CHIP_MODE</i> callback in conjunction with the <a href="..\parallel\nc-parallel-pparallel_set_chip_mode.md">PPARALLEL_SET_CHIP_MODE</a> callback.

To set a mode, a caller must first clear the current mode.

For more information, see <a href="https://msdn.microsoft.com/a22cdeef-4ae7-49f8-b0b5-a4d68feb4235">Setting and Clearing the Communication Mode on a ParallelPort</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_set_chip_mode.md">IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ns-parallel-_parallel_pnp_information.md">PARALLEL_PNP_INFORMATION</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_clear_chip_mode.md">IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_set_chip_mode.md">PPARALLEL_SET_CHIP_MODE</a>



 

 


