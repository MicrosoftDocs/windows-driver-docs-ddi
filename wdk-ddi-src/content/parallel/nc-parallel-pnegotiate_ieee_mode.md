---
UID: NC:parallel.PNEGOTIATE_IEEE_MODE
title: PNEGOTIATE_IEEE_MODE
author: windows-driver-content
description: The PNEGOTIATE_IEEE_MODE-typed callback routine selects the fastest forward and reverse protocols that the system-supplied bus driver for parallel ports supports from among those specified by the caller.
old-location: parports\pnegotiate_ieee_mode.htm
old-project: parports
ms.assetid: 2cf3564e-10aa-49bb-9b94-abd987870196
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RegisterOpRegionHandler
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
req.alt-api: PNEGOTIATE_IEEE_MODE
req.alt-loc: parallel.h
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
req.typenames: *LPRILGBATOKEN, RILGBATOKEN
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

### -param Context [in]

Pointer to the device extension of a parallel device's physical device object (<a href="wdkgloss.p#wdkgloss.pdo#wdkgloss.pdo"><i>PDO</i></a>).


### -param ModeMaskFwd [in]

Specifies the forward protocols. <i>ModeMaskFwd</i> is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports. For the forward and reverse protocol values, see the protocol constants defined in <i>ntddpar.h</i> (from NONE to ECP_ANY).


### -param ModeMaskRev [in]

Specifies the reverse protocols. <i>ModeMaskRev </i>is a bitwise OR of the constants that represent the protocols that the parallel port bus driver supports.


### -param ModeSafety [in]

Specifies the safety mode. Must be set to the SAFE_MODE enumeration value of the PARALLEL_SAFETY enumeration type:

<pre class="syntax" xml:space="preserve"><code>typedef enum {
  SAFE_MODE,
  UNSAFE_MODE
} PARALLEL_SAFETY;</code></pre>

### -param IsForward [in]

Specifies whether to connect the forward or the reverse protocol that the routine negotiates. If <i>IsForward</i> is <b>TRUE</b>, the forward protocol is connected. Otherwise, the reverse protocol is connected.


## -returns
<dl>
<dt><b>STATUS_SUCCESSFUL</b></dt>
</dl>The IEEE mode was successfully negotiated.
<dl>
<dt><b>STATUS_DEVICE_PROTOCOL_ERROR</b></dt>
</dl>An IEEE mode is already set on the device.
<dl>
<dt><b>STATUS_<i>Xxx</i></b></dt>
</dl>An internal operation resulted in an NTSTATUS error.

 


## -remarks
To obtain a pointer to the system-supplied PNEGOTIATE_IEEE_MODE callback, a kernel-mode driver uses an <a href="..\parallel\ni-parallel-ioctl_internal_parclass_connect.md">IOCTL_INTERNAL_PARCLASS_CONNECT</a> request, which returns a <a href="..\parallel\ns-parallel-_parclass_information.md">PARCLASS_INFORMATION</a> structure. The <b>NegotiateIeeeMode</b> member of the PARCLASS_INFORMATION structure is a pointer to this callback.

The PNEGOTIATE_IEEE_MODE callback runs in the caller's thread at the IRQL of the caller.


## -see-also
<dl>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>
</dt>
<dt>
<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_default_modes.md">IOCTL_PAR_GET_DEFAULT_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pdetermine_ieee_modes.md">PDETERMINE_IEEE_MODES</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_ieee_fwd_to_rev.md">PPARALLEL_IEEE_FWD_TO_REV</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pparallel_ieee_rev_to_fwd.md">PPARALLEL_IEEE_REV_TO_FWD</a>
</dt>
<dt>
<a href="..\parallel\nc-parallel-pterminate_ieee_mode.md">PTERMINATE_IEEE_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PNEGOTIATE_IEEE_MODE function pointer%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

