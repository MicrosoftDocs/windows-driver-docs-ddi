---
UID: NI:ntddpar.IOCTL_PAR_GET_DEFAULT_MODES
title: IOCTL_PAR_GET_DEFAULT_MODES (ntddpar.h)
description: The IOCTL_PAR_GET_DEFAULT_MODES request returns the default write (forward) and read (reverse) IEEE 1284 protocols that the system-supplied bus driver for parallel ports uses.
old-location: parports\ioctl_par_get_default_modes.htm
tech.root: parports
ms.date: 02/15/2018
keywords: ["IOCTL_PAR_GET_DEFAULT_MODES IOCTL"]
ms.keywords: IOCTL_PAR_GET_DEFAULT_MODES, IOCTL_PAR_GET_DEFAULT_MODES control code [Parallel Ports], cisspd_29dfce16-6dea-4bff-928d-6ab83099595c.xml, ntddpar/IOCTL_PAR_GET_DEFAULT_MODES, parports.ioctl_par_get_default_modes
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
targetos: Windows
req.typenames: OFFLOAD_SECURITY_ASSOCIATION, *POFFLOAD_SECURITY_ASSOCIATION
f1_keywords:
 - IOCTL_PAR_GET_DEFAULT_MODES
 - ntddpar/IOCTL_PAR_GET_DEFAULT_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddpar.h
api_name:
 - IOCTL_PAR_GET_DEFAULT_MODES
---

# IOCTL_PAR_GET_DEFAULT_MODES IOCTL


##  Major Code:


[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)


## -description

The IOCTL_PAR_GET_DEFAULT_MODES request returns the default write (forward) and read (reverse) IEEE 1284 protocols that the system-supplied bus driver for parallel ports uses. The default write protocol is CENTRONICS; the default read protocol is NIBBLE.

For more information, see <a href="/previous-versions/ff544797(v=vs.85)">Setting and Clearing a Communication Mode for a Parallel Device</a>.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None.

### -input-buffer-length

None.

### -output-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a PARCLASS_NEGOTIATION_MASK structure that the client allocates to output mode information. The system-supplied bus driver for parallel ports sets the <b>usReadMask</b> member and the <b>usWriteMask</b> member. The default write mode is CENTRONICS; the default read mode is NIBBLE.

### -output-buffer-length

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a <a href="..\ntddpar\ns-ntddpar-_parclass_negotiation_mask.md">PARCLASS_NEGOTIATION_MASK</a> structure.

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a PARCLASS_NEGOTIATION_MASK structure. Otherwise, <b>Information</b> is set to zero.

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to the following value:




**STATUS_BUFFER_TOO_SMALL**

The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> is less than the size, in bytes, of a PARCLASS_NEGOTIATION_MASK structure.

## -see-also

<a href="..\ntddpar\ns-ntddpar-_parclass_negotiation_mask.md">PARCLASS_NEGOTIATION_MASK</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_get_device_caps.md">IOCTL_PAR_GET_DEVICE_CAPS</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_get_mode.md">IOCTL_IEEE1284_GET_MODE</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_ieee1284_negotiate.md">IOCTL_IEEE1284_NEGOTIATE</a>
