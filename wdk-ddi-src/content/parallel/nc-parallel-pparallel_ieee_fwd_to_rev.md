---
UID: NC:parallel.PPARALLEL_IEEE_FWD_TO_REV
title: PPARALLEL_IEEE_FWD_TO_REV (parallel.h)
description: The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_ieee_fwd_to_rev.htm
tech.root: parports
ms.assetid: cb7e01e3-7aff-436c-af82-bc7716d2fe1f
ms.date: 02/15/2018
keywords: ["PPARALLEL_IEEE_FWD_TO_REV callback"]
ms.keywords: PPARALLEL_IEEE_FWD_TO_REV, PPARALLEL_IEEE_FWD_TO_REV function pointer [Parallel Ports], cisspd_a22a220b-a633-48b8-9e53-434f362d15f0.xml, parallel/PPARALLEL_IEEE_FWD_TO_REV, parports.pparallel_ieee_fwd_to_rev
f1_keywords:
 - "parallel/PPARALLEL_IEEE_FWD_TO_REV"
 - "PPARALLEL_IEEE_FWD_TO_REV"
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
- PPARALLEL_IEEE_FWD_TO_REV
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_IEEE_FWD_TO_REV callback


## -description


The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


```cpp
typedef NTSTATUS ( *PPARALLEL_IEEE_FWD_TO_REV)(
  _In_ PVOID Context
);
```


## -parameters




### -param Context 
[in]
Pointer to a device extension of a parallel device's physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>).


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
The transfer mode was changed from forward to reverse.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl>
</td>
<td width="60%">
An internal operation resulted in an NTSTATUS error.

</td>
</tr>
</table>
 




## -remarks



To obtain a pointer to the system-supplied PPARALLEL_IEEE_FWD_TO_REV callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>IeeeFwdToRevMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

If the device is connected and in the reverse mode, the PPARALLEL_IEEE_FWD_TO_REV callback returns without further processing. Otherwise, the callback puts the parallel device into reverse mode and connects a previously negotiated reverse protocol. The <a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a> callback can be used to negotiate the reverse protocol.

The PPARALLEL_IEEE_FWD_TO_REV callback runs in the caller's thread at the caller's IRQL.




## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



 

 


