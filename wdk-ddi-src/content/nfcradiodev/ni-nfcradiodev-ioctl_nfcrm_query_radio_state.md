---
UID: NI:nfcradiodev.IOCTL_NFCRM_QUERY_RADIO_STATE
title: IOCTL_NFCRM_QUERY_RADIO_STATE (nfcradiodev.h)
description: This IOCTL is used by the radio management application or service to query the current radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcrm_query_radio_state.htm
tech.root: nfpdrivers
ms.assetid: BEFA6568-3E89-4626-AAC2-A0C628E5429F
ms.date: 02/15/2018
ms.keywords: IOCTL_NFCRM_QUERY_RADIO_STATE, IOCTL_NFCRM_QUERY_RADIO_STATE control, IOCTL_NFCRM_QUERY_RADIO_STATE control code [Near-Field Proximity Drivers], nfcradiodev/IOCTL_NFCRM_QUERY_RADIO_STATE, nfpdrivers.ioctl_nfcrm_query_radio_state
f1_keywords:
 - "nfcradiodev/IOCTL_NFCRM_QUERY_RADIO_STATE"
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
- IOCTL_NFCRM_QUERY_RADIO_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_NFCRM_QUERY_RADIO_STATE IOCTL


## -description


This IOCTL is used by the radio management application or service to query the current radio power state of the proximity device.


## -ioctlparameters




### -input-buffer

None


### -input-buffer-length

None


### -output-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcradiodev/ns-nfcradiodev-_nfcrm_radio_state"> NFCRM_RADIO_STATE structure</a>



### -output-buffer-length

sizeof(NFCRM_RADIO_STATE)


### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful.


## -remarks



The <b>STATUS_INVALID_PARAMETER</b> return code is no longer required. A bug was discovered in Windows 10 build 10240, that Windows would send a non-null input parameter with this IOCTL. This bug was fixed in later versions of Windows. To simplify code, drivers can ignore the input parameters in all versions of Windows 10.



