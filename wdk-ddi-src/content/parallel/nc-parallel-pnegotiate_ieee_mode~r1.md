---
UID: NC:parallel.PNEGOTIATE_IEEE_MODE~r1
tech.root: parports
title: PNEGOTIATE_IEEE_MODE
ms.date: 07/24/2025
targetos: Windows
description: The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller.
prerelease: false
keywords: ["PNEGOTIATE_IEEE_MODE callback"]
ms.keywords: PNEGOTIATE_IEEE_MODE, PNEGOTIATE_IEEE_MODE function pointer [Parallel Ports], cisspd_0bea0bb3-2a7c-4cf4-938d-8bc67962a222.xml, parallel/PNEGOTIATE_IEEE_MODE, parports.pnegotiate_ieee_mode
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: parallel.h
req.idl: 
req.include-header: parallel.h
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Desktop
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - parallel.h
api_name:
 - PNEGOTIATE_IEEE_MODE
f1_keywords:
 - PNEGOTIATE_IEEE_MODE
 - parallel/PNEGOTIATE_IEEE_MODE
dev_langs:
 - c++
helpviewer_keywords:
 - PNEGOTIATE_IEEE_MODE
---

## -description

The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller. The system-supplied bus driver for parallel ports supplies this routine.

## -parameters

### -param Context [in]

Pointer to the device extension of a parallel device's physical device object ([PDO](/windows-hardware/drivers/)).

### -param ModeMaskFwd [in]

Specifies the forward protocols. *ModeMaskFwd* is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports. For the forward and reverse protocol values, see the protocol constants defined in *ntddpar.h* (from NONE to ECP_ANY).

### -param ModeMaskRev [in]

Specifies the reverse protocols. *ModeMaskRev* is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports.

### -param ModeSafety [in]

Specifies the safety mode. Must be set to the SAFE_MODE enumeration value of the PARALLEL_SAFETY enumeration type:

``` cpp
typedef enum {
  SAFE_MODE,
  UNSAFE_MODE
} PARALLEL_SAFETY;
```

### -param IsForward [in]

Specifies whether to connect the forward or the reverse protocol that the routine negotiates. If *IsForward* is **TRUE**, the forward protocol is connected. Otherwise, the reverse protocol is connected.

## -returns

| Return code | Description |
|--|--|
| STATUS_SUCCESSFUL | The IEEE mode was successfully negotiated. |
| STATUS_DEVICE_PROTOCOL_ERROR | An IEEE mode is already set on the device. |
| STATUS_*Xxx* | An internal operation resulted in an NTSTATUS error. |

## -remarks

To obtain a pointer to the system-supplied PNEGOTIATE_IEEE_MODE callback, a kernel-mode driver uses an [IOCTL_INTERNAL_PARCLASS_CONNECT](..\parallel\ni-parallel-ioctl_internal_parclass_connect.md) request, which returns a [PARCLASS_INFORMATION](..\parallel\ns-parallel-_parclass_information.md) structure. The **NegotiateIeeeMode** member of the PARCLASS_INFORMATION structure is a pointer to this callback.

The PNEGOTIATE_IEEE_MODE callback runs in the caller's thread at the IRQL of the caller.

## -see-also

- [IOCTL_PAR_GET_DEFAULT_MODES](..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md)
- [IOCTL_IEEE1284_GET_MODE](..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md)
- [PTERMINATE_IEEE_MODE](..\parallel\nc-parallel-pterminate_ieee_mode.md)
- [PPARALLEL_IEEE_FWD_TO_REV](..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md)
- [IOCTL_IEEE1284_NEGOTIATE](..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md)
- [PDETERMINE_IEEE_MODES](..\parallel\nc-parallel-pdetermine_ieee_modes.md)
- [PPARALLEL_IEEE_REV_TO_FWD](..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md)
