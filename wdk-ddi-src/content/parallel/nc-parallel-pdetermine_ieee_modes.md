---
UID: NC:parallel.PDETERMINE_IEEE_MODES
title: PDETERMINE_IEEE_MODES
author: windows-driver-content
description: The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pdetermine_ieee_modes.htm
old-project: parports
ms.assetid: 9f57337b-20b8-4aa6-a303-0972cd0c92cf
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PDETERMINE_IEEE_MODES, PDETERMINE_IEEE_MODES function pointer [Parallel Ports], cisspd_da5c1f0b-cec4-48a4-b460-9b09751531a5.xml, parallel/PDETERMINE_IEEE_MODES, parports.pdetermine_ieee_modes
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	parallel.h
apiname:
-	PDETERMINE_IEEE_MODES
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PDETERMINE_IEEE_MODES callback


## -description


The PDETERMINE_IEEE_MODES-typed callback routine determines which IEEE 1284 protocols a parallel device supports. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


````
typedef USHORT ( *PDETERMINE_IEEE_MODES)(
  _In_ PVOID Context
);
````


## -parameters




### -param Context [in]

Pointer to a device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


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

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>



<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PDETERMINE_IEEE_MODES function pointer%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

