---
UID: NC:parallel.PTERMINATE_IEEE_MODE
title: PTERMINATE_IEEE_MODE
author: windows-driver-content
description: The PTERMINATE_IEEE_MODE-typed callback routine terminates the current IEEE operating mode and sets the mode to IEEE 1284-compatible. The system-supplied bus driver for parallel ports supplies this routine.
old-location: parports\pterminate_ieee_mode.htm
old-project: parports
ms.assetid: 35c4f348-aeaa-4e6e-8cc5-62d78beaa434
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: parports.pterminate_ieee_mode, PTERMINATE_IEEE_MODE function pointer [Parallel Ports], PTERMINATE_IEEE_MODE, parallel/PTERMINATE_IEEE_MODE, cisspd_97e0ba9c-746e-4f7a-8d52-a321d6a18a4b.xml
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
-	PTERMINATE_IEEE_MODE
product: Windows
targetos: Windows
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
---

# PTERMINATE_IEEE_MODE callback


## -description


The PTERMINATE_IEEE_MODE-typed callback routine terminates the current IEEE operating mode and sets the mode to IEEE 1284-compatible. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


````
typedef NTSTATUS ( *PTERMINATE_IEEE_MODE)(
  _In_ PVOID Context
);
````


## -parameters




### -param Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


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
The operating mode was set to IEEE 1284-compatible mode.

</td>
</tr>
</table> 



## -remarks


To obtain a pointer to the system-supplied PTERMINATE_IEEE_MODE callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>TerminateIeeeMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

The PTERMINATE_IEEE_MODE callback runs in the caller's thread at the IRQL of the caller.

For more information, see <a href="https://msdn.microsoft.com/2ff53ed0-dbb7-4c8f-b6e4-5f7d20124a7c">Setting and Clearing a Communication Mode for a Parallel Device</a>.



## -see-also

<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>

<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>

<a href="..\parallel\nc-parallel-pnegotiate_ieee_mode.md">PNEGOTIATE_IEEE_MODE</a>

<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PTERMINATE_IEEE_MODE function pointer%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

