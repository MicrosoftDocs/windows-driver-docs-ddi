---
UID: NI:nfcradiodev.IOCTL_NFCSERM_SET_RADIO_STATE
title: IOCTL_NFCSERM_SET_RADIO_STATE (nfcradiodev.h)
description: This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcserm_set_radio_state.htm
tech.root: nfpdrivers
ms.assetid: 721AE7FE-927C-4EBA-B33D-C5A5A986951C
ms.date: 02/15/2018
keywords: ["IOCTL_NFCSERM_SET_RADIO_STATE IOCTL"]
ms.keywords: IOCTL_NFCSERM_SET_RADIO_STATE, IOCTL_NFCSERM_SET_RADIO_STATE control, IOCTL_NFCSERM_SET_RADIO_STATE control code [Near-Field Proximity Drivers], nfcradiodev/IOCTL_NFCSERM_SET_RADIO_STATE, nfpdrivers.ioctl_nfcserm_set_radio_state
req.header: nfcradiodev.h
req.include-header: 
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
req.typenames: 
f1_keywords:
 - IOCTL_NFCSERM_SET_RADIO_STATE
 - nfcradiodev/IOCTL_NFCSERM_SET_RADIO_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfcradiodev.h
api_name:
 - IOCTL_NFCSERM_SET_RADIO_STATE
---

# IOCTL_NFCSERM_SET_RADIO_STATE IOCTL


## -description

This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.

## -ioctlparameters

### -input-buffer

<a href="/windows-hardware/drivers/ddi/nfcradiodev/ns-nfcradiodev-_nfcrm_set_radio_state"> NFCRM_SET_RADIO_STATE structure</a>

### -input-buffer-length

sizeof(NFCRM_SET_RADIO_STATE)

### -output-buffer

None

### -output-buffer-length

None

### -in-out-buffer

### -inout-buffer-length

### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td><b>STATUS_INVALID_DEVICE_STATE</b></td>
<td>This code is returned when the device is already in the proximity radio power state that is being set by the client.</td>
</tr>
<tr>
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td>This code is returned when the output buffer is non-zero.</td>
</tr>
</table>