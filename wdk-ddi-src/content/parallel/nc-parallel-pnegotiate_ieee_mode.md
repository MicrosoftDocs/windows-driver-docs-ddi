---
UID: NC:parallel.PNEGOTIATE_IEEE_MODE
title: PNEGOTIATE_IEEE_MODE
author: windows-driver-content
description: The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller.
old-location: parports\pnegotiate_ieee_mode.htm
old-project: parports
ms.assetid: 2cf3564e-10aa-49bb-9b94-abd987870196
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PNEGOTIATE_IEEE_MODE, PNEGOTIATE_IEEE_MODE function pointer [Parallel Ports], cisspd_0bea0bb3-2a7c-4cf4-938d-8bc67962a222.xml, parallel/PNEGOTIATE_IEEE_MODE, parports.pnegotiate_ieee_mode
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	parallel.h
api_name:
-	PNEGOTIATE_IEEE_MODE
product: Windows
targetos: Windows
req.typenames: RILGBATOKEN, *LPRILGBATOKEN
---

# PNEGOTIATE_IEEE_MODE callback


## -description


The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller. The system-supplied bus driver for parallel ports supplies this routine.


## -prototype


````
typedef NTSTATUS  ( *PNEGOTIATE_IEEE_MODE)(
  _In_ PVOID           Context,
  _In_ USHORT          ModeMaskFwd,
  _In_ USHORT          ModeMaskRev,
  _In_ PARALLEL_SAFETY ModeSafety,
  _In_ BOOLEAN         IsForward
);
````


## -parameters




### -param Extension


### -param Extensibility








#### - Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PDO</a>).


#### - IsForward [in]

Specifies whether to connect the forward or the reverse protocol that the routine negotiates. If <i>IsForward</i> is <b>TRUE</b>, the forward protocol is connected. Otherwise, the reverse protocol is connected.


#### - ModeMaskFwd [in]

Specifies the forward protocols. <i>ModeMaskFwd</i> is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports. For the forward and reverse protocol values, see the protocol constants defined in <i>ntddpar.h</i> (from NONE to ECP_ANY).


#### - ModeMaskRev [in]

Specifies the reverse protocols. <i>ModeMaskRev </i>is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports.


#### - ModeSafety [in]

Specifies the safety mode. Must be set to the SAFE_MODE enumeration value of the PARALLEL_SAFETY enumeration type:

<pre class="syntax" xml:space="preserve"><code>typedef enum {
  SAFE_MODE,
  UNSAFE_MODE
} PARALLEL_SAFETY;</code></pre>

## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The IEEE mode was successfully negotiated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_PROTOCOL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An IEEE mode is already set on the device.

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



To obtain a pointer to the system-supplied PNEGOTIATE_IEEE_MODE callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>NegotiateIeeeMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

The PNEGOTIATE_IEEE_MODE callback runs in the caller's thread at the IRQL of the caller.




## -see-also

<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>



<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>



<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



 

 


