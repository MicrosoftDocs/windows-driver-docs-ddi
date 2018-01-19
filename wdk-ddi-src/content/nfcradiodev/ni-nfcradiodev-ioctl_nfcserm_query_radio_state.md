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
ms.keywords: _NFC_CX_RF_DISCOVERY_CONFIG, NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
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
req.alt-api: IOCTL_NFCSERM_QUERY_RADIO_STATE
req.alt-loc: nfcradiodev.h
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
req.typenames: NFC_CX_RF_DISCOVERY_CONFIG, *PNFC_CX_RF_DISCOVERY_CONFIG
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

<a href="..\nfcradiodev\ns-nfcradiodev-_nfcrm_set_radio_state.md"> NFCRM_RADIO_STATE structure</a>



### -output-buffer-length
sizeof(NFCRM_RADIO_STATE)


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
