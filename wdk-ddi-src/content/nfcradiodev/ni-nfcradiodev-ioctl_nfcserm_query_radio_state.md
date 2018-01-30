---
UID: NI:nfcradiodev.IOCTL_NFCSERM_QUERY_RADIO_STATE
title: IOCTL_NFCSERM_QUERY_RADIO_STATE
author: windows-driver-content
description: This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcserm_query_radio_state.htm
old-project: nfpdrivers
ms.assetid: 625E3B0B-78B4-4C12-B1FD-555FAA5E0E19
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.ioctl_nfcserm_query_radio_state, IOCTL_NFCSERM_QUERY_RADIO_STATE, _IOCTL_NFCSERM_QUERY_RADIO_STATE, IOCTL_NFCSERM_QUERY_RADIO_STATE control code [Near-Field Proximity Drivers], IOCTL_NFCSERM_QUERY_RADIO_STATE, nfcradiodev/IOCTL_NFCSERM_QUERY_RADIO_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	nfcradiodev.h
apiname:
-	IOCTL_NFCSERM_QUERY_RADIO_STATE
product: Windows
targetos: Windows
req.typenames: NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
---

# IOCTL_NFCSERM_QUERY_RADIO_STATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


This IOCTL is used by the SE radio management application or service to query the current radio power state of the proximity device.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer


<a href="..\nfcradiodev\ns-nfcradiodev-_nfcrm_set_radio_state.md"> NFCRM_RADIO_STATE structure</a>



### -output-buffer-length

sizeof(NFCRM_RADIO_STATE)


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:
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

