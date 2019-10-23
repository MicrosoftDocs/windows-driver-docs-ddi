---
UID: NI:nfcradiodev.IOCTL_NFCSERM_QUERY_RADIO_STATE
title: IOCTL_NFCSERM_QUERY_RADIO_STATE (nfcradiodev.h)
description: This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcserm_query_radio_state.htm
tech.root: nfpdrivers
ms.assetid: 625E3B0B-78B4-4C12-B1FD-555FAA5E0E19
ms.date: 02/15/2018
ms.keywords: IOCTL_NFCSERM_QUERY_RADIO_STATE, IOCTL_NFCSERM_QUERY_RADIO_STATE control, IOCTL_NFCSERM_QUERY_RADIO_STATE control code [Near-Field Proximity Drivers], _IOCTL_NFCSERM_QUERY_RADIO_STATE, nfcradiodev/IOCTL_NFCSERM_QUERY_RADIO_STATE, nfpdrivers.ioctl_nfcserm_query_radio_state
ms.topic: ioctl
f1_keywords:
 - "nfcradiodev/IOCTL_NFCSERM_QUERY_RADIO_STATE"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- nfcradiodev.h
api_name:
- IOCTL_NFCSERM_QUERY_RADIO_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_NFCSERM_QUERY_RADIO_STATE IOCTL


## -description


This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcradiodev/ns-nfcradiodev-_nfcrm_set_radio_state"> NFCRM_RADIO_STATE structure</a>



### -output-buffer-length

sizeof(NFCRM_RADIO_STATE)


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
<td><b>STATUS_INVALID_PARAMETER</b></td>
<td> This code is returned when the input buffer is non-zero.</td>
</tr>
</table>
 

