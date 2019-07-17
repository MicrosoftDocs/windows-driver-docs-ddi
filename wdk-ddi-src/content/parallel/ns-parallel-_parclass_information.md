---
UID: NS:parallel._PARCLASS_INFORMATION
title: _PARCLASS_INFORMATION (parallel.h)
description: The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device.
old-location: parports\parclass_information.htm
tech.root: parports
ms.assetid: abad8ebd-a9fc-4cfb-8495-aca4e38ee45a
ms.date: 02/15/2018
ms.keywords: "*PPARCLASS_INFORMATION, PARCLASS_INFORMATION, PARCLASS_INFORMATION structure [Parallel Ports], PPARCLASS_INFORMATION, PPARCLASS_INFORMATION structure pointer [Parallel Ports], _PARCLASS_INFORMATION, cisspd_b7b1d8b8-fc86-4bd9-a474-e31f416da93c.xml, parallel/PARCLASS_INFORMATION, parallel/PPARCLASS_INFORMATION, parports.parclass_information"
ms.topic: struct
f1_keywords:
 - "parallel/PARCLASS_INFORMATION"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- parallel.h
api_name:
- PARCLASS_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# _PARCLASS_INFORMATION structure


## -description


The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device.


## -syntax


```cpp
typedef struct _PARCLASS_INFORMATION {
  PUCHAR                    Controller;
  ULONG                     SpanOfController;
  PDETERMINE_IEEE_MODES     DetermineIeeeModes;
  PNEGOTIATE_IEEE_MODE      NegotiateIeeeMode;
  PTERMINATE_IEEE_MODE      TerminateIeeeMode;
  PPARALLEL_IEEE_FWD_TO_REV IeeeFwdToRevMode;
  PPARALLEL_IEEE_REV_TO_FWD IeeeRevToFwdMode;
  PPARALLEL_READ            ParallelRead;
  PPARALLEL_WRITE           ParallelWrite;
  PVOID                     ParclassContext;
  ULONG                     HardwareCapabilities;
  ULONG                     FifoDepth;
  ULONG                     FifoWidth;
} PARCLASS_INFORMATION, *PPARCLASS_INFORMATION;
```


## -struct-fields




### -field Controller

Specifies the base I/O address allocated to a parallel port.


### -field EcrController




### -field SpanOfController

Specifies the range in bytes of I/O address space allocated to a parallel port.


### -field DetermineIeeeModes

Pointer to the <a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a> callback routine that determines which IEEE protocols a parallel device supports.


### -field NegotiateIeeeMode

Pointer to the <a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a> callback routine that negotiates the fastest protocol that the system-supplied bus driver for parallel ports supports from among those specified by the caller.


### -field TerminateIeeeMode

Pointer to the <a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a> callback routine that terminates the current IEEE mode and sets the mode to IEEE_COMPATIBILITY.


### -field IeeeFwdToRevMode

Pointer to the <a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a> callback routine that changes the transfer mode from forward to reverse.


### -field IeeeRevToFwdMode

Pointer to the <a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a> callback routine that changes the transfer mode from reverse to forward.


### -field ParallelRead

Pointer to the <a href="..\parallel\nc-parallel-pparallel_read.md">PPARALLEL_READ</a> callback routine that a client can use to read from a parallel device.


### -field ParallelWrite

Pointer to the <a href="..\parallel\nc-parallel-pparallel_write.md">PPARALLEL_WRITE</a> callback routine that a client can use to write to a parallel device.


### -field ParclassContext

Pointer to the device extension of a parallel device's physical device object (<a href="https://docs.microsoft.com/windows-hardware/drivers/">PDO</a>).


### -field HardwareCapabilities

Specifies which hardware capabilities are present. <b>HardwareCapabilities</b> is a bitwise OR of one or more of the following flags:





#### PPT_NO_HARDWARE_PRESENT



#### PPT_ECP_PRESENT



#### PPT_EPP_PRESENT



#### PPT_EPP_32_PRESENT

32-bit reads and writes are supported.



#### PPT_BYTE_PRESENT



#### PPT_BIDI_PRESENT



#### PPT_1284_3_PRESENT


### -field FifoDepth

Specifies the size, in words, of the ECP FIFO. The ECP FIFO word size, in bits, is the value of <b>FifoWidth</b>.


### -field FifoWidth

Specifies the ECP FIFO word size, in bits, which is the number of bits handled in parallel.


### -field ParallelTryselect




### -field ParallelDeSelect






## -remarks



A kernel-mode driver can obtain this information from the system-supplied bus driver for parallel ports using an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request. The system-supplied bus driver for parallel ports supplies all the callback routines.

A client uses this information to operate a parallel port and to read and write a parallel device. The callback routines can only be used by a driver that holds a lock on the parent parallel port. A driver obtains a lock by using an <a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a> request.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff543942(v=vs.85)">Connecting to a Parallel Device</a>.




## -see-also

<a href="..\parallel\nc-parallel-pparallel_write.md">PPARALLEL_WRITE</a>



<a href="..\parallel\nc-parallel-pparallel_read.md">PPARALLEL_READ</a>



<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>



<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a>



<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



 

 


