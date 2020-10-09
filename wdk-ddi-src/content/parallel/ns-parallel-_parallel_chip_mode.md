---
UID: NS:parallel._PARALLEL_CHIP_MODE
title: _PARALLEL_CHIP_MODE (parallel.h)
description: The PARALLEL_CHIP_MODE structure specifies the operating mode of a parallel port.
old-location: parports\parallel_chip_mode.htm
tech.root: parports
ms.assetid: e9d78c80-e6cf-49af-89de-6df8ea871796
ms.date: 02/15/2018
keywords: ["PARALLEL_CHIP_MODE structure"]
ms.keywords: "*PPARALLEL_CHIP_MODE, PARALLEL_CHIP_MODE, PARALLEL_CHIP_MODE structure [Parallel Ports], PPARALLEL_CHIP_MODE, PPARALLEL_CHIP_MODE structure pointer [Parallel Ports], _PARALLEL_CHIP_MODE, cisspd_1dbc3693-e551-46a3-9a41-725b06a2ee9a.xml, parallel/PARALLEL_CHIP_MODE, parallel/PPARALLEL_CHIP_MODE, parports.parallel_chip_mode"
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
targetos: Windows
req.typenames: PARALLEL_CHIP_MODE, *PPARALLEL_CHIP_MODE
f1_keywords:
 - _PARALLEL_CHIP_MODE
 - parallel/_PARALLEL_CHIP_MODE
 - PPARALLEL_CHIP_MODE
 - parallel/PPARALLEL_CHIP_MODE
 - PARALLEL_CHIP_MODE
 - parallel/PARALLEL_CHIP_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - parallel.h
api_name:
 - PARALLEL_CHIP_MODE
---

# _PARALLEL_CHIP_MODE structure


## -description

The PARALLEL_CHIP_MODE structure specifies the operating mode of a parallel port.

## -struct-fields

### -field ModeFlags

Specifies an operating mode of a parallel port, either an enhanced parallel port (EPP) mode or an extended capabilities port (ECP) mode.

### -field success

Not used.

## -syntax

```cpp
typedef struct _PARALLEL_CHIP_MODE {
  UCHAR   ModeFlags;
  BOOLEAN success;
} PARALLEL_CHIP_MODE, *PPARALLEL_CHIP_MODE;
```

## -remarks

A client uses a PARALLEL_CHIP_MODE structure with internal device control requests to set and clear the operating mode of a parallel port.

<div class="alert"><b>Note</b>    Microsoft does not recommend using a client-supplied interrupt routine. The use of interrupts might cause system instability. By default, the <a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a> request is disabled. For more information, see <a href="/previous-versions/ff543934(v=vs.85)">Connecting an Interrupt Service Routine to a ParallelPort</a>.</div>
<div> </div>

## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_parallel_set_chip_mode.md">IOCTL_INTERNAL_PARALLEL_SET_CHIP_MODE</a>



<a href="..\parallel\ni-parallel-ioctl_internal_get_parallel_port_info.md">IOCTL_INTERNAL_GET_PARALLEL_PORT_INFO</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_connect_interrupt.md">IOCTL_INTERNAL_PARALLEL_CONNECT_INTERRUPT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parallel_clear_chip_mode.md">IOCTL_INTERNAL_PARALLEL_CLEAR_CHIP_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_set_chip_mode.md">PPARALLEL_SET_CHIP_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_clear_chip_mode.md">PPARALLEL_CLEAR_CHIP_MODE</a>