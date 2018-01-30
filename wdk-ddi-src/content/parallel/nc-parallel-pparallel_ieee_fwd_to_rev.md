---
UID: NC:parallel.PPARALLEL_IEEE_FWD_TO_REV
title: PPARALLEL_IEEE_FWD_TO_REV
author: windows-driver-content
description: The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pparallel_ieee_fwd_to_rev.htm
old-project: parports
ms.assetid: cb7e01e3-7aff-436c-af82-bc7716d2fe1f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.pparallel_ieee_fwd_to_rev, PPARALLEL_IEEE_FWD_TO_REV function pointer [Parallel Ports], PPARALLEL_IEEE_FWD_TO_REV, parallel/PPARALLEL_IEEE_FWD_TO_REV, cisspd_a22a220b-a633-48b8-9e53-434f362d15f0.xml
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
-	PPARALLEL_IEEE_FWD_TO_REV
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PPARALLEL_IEEE_FWD_TO_REV callback


## -description


The PPARALLEL_IEEE_FWD_TO_REV-typed callback routine changes the transfer mode from forward to reverse. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


````
typedef NTSTATUS ( *PPARALLEL_IEEE_FWD_TO_REV)(
  _In_ PVOID Context
);
````


## -parameters




### -param Context [in]

Pointer to a device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


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

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>

<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>

<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>

<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>

<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PPARALLEL_IEEE_FWD_TO_REV function pointer%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

