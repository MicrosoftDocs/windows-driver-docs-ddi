---
UID: NS:parallel._PARCLASS_INFORMATION
title: "_PARCLASS_INFORMATION"
author: windows-driver-content
description: The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device.
old-location: parports\parclass_information.htm
old-project: parports
ms.assetid: abad8ebd-a9fc-4cfb-8495-aca4e38ee45a
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PPARCLASS_INFORMATION, PARCLASS_INFORMATION, PARCLASS_INFORMATION structure [Parallel Ports], PPARCLASS_INFORMATION, PPARCLASS_INFORMATION structure pointer [Parallel Ports], _PARCLASS_INFORMATION, cisspd_b7b1d8b8-fc86-4bd9-a474-e31f416da93c.xml, parallel/PARCLASS_INFORMATION, parallel/PPARCLASS_INFORMATION, parports.parclass_information"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	PARCLASS_INFORMATION
product: Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# _PARCLASS_INFORMATION structure


## -description


The PARCLASS_INFORMATION structure specifies information about a parallel port, pointers to callback routines to operate a parallel port, and pointers to callback routines to read and write to a parallel device.


## -syntax


````
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
````


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

Pointer to the device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


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

For more information, see <a href="https://msdn.microsoft.com/c05a1a1e-308a-4b9f-af43-761c4c14d6af">Connecting to a Parallel Device</a>.




## -see-also

<a href="..\parallel\ni-parallel-ioctl_internal_lock_port.md">IOCTL_INTERNAL_LOCK_PORT</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>



<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



<a href="..\parallel\nc-parallel-pparallel_read.md">PPARALLEL_READ</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



<a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a>



<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>



<a href="..\parallel\nc-parallel-pparallel_write.md">PPARALLEL_WRITE</a>



<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PARCLASS_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

