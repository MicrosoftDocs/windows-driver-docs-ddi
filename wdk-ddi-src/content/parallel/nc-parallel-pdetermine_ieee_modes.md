---
UID: NC:parallel.PDETERMINE_IEEE_MODES
title: PDETERMINE_IEEE_MODES (parallel.h)
description: The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pdetermine_ieee_modes.htm
tech.root: parports
ms.assetid: 9f57337b-20b8-4aa6-a303-0972cd0c92cf
ms.date: 02/15/2018
keywords: ["PDETERMINE_IEEE_MODES callback"]
ms.keywords: PDETERMINE_IEEE_MODES, PDETERMINE_IEEE_MODES function pointer [Parallel Ports], cisspd_da5c1f0b-cec4-48a4-b460-9b09751531a5.xml, parallel/PDETERMINE_IEEE_MODES, parports.pdetermine_ieee_modes
f1_keywords:
 - "parallel/PDETERMINE_IEEE_MODES"
 - "PDETERMINE_IEEE_MODES"
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
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- parallel.h
api_name:
- PDETERMINE_IEEE_MODES
product:
- Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PDETERMINE_IEEE_MODES callback


## -description


The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef USHORT ( *PDETERMINE_IEEE_MODES)(
  _In_ PVOID Context
);
```


## -parameters




### -param Context [in]

Pointer to a device extension of a parallel device's physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>).


## -returns



The return value indicates which protocols a parallel device supports. The return value is a bitwise OR of one or more of the following constants that represent the protocols that are supported by the system-supplied bus driver for parallel ports. The protocol constants are listed in order of decreasing data transfer rate.

BOUNDED_ECP

ECP_HW_NOIRQ

EPP_HW

EPP_SW

ECP_SW

IEEE_COMPATIBILITY

CENTRONICS

NONE




## -remarks



To obtain a pointer to the system-supplied PDETERMINE_IEEE_MODES callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>DetermineIeeeModes</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

The PDETERMINE_IEEE_MODES callback runs in the caller's thread at the IRQL of the caller.




## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



 

 


