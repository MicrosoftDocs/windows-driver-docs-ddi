---
UID: NI:nfcradiodev.IOCTL_NFCRM_SET_RADIO_STATE
title: IOCTL_NFCRM_SET_RADIO_STATE (nfcradiodev.h)
description: This IOCTL is used by the radio management application or service to set the radio power state of the proximity device.
old-location: nfpdrivers\ioctl_nfcrm_set_radio_state.htm
tech.root: nfpdrivers
ms.assetid: C54C774A-3FBB-4850-BBB2-2B330CC64A8D
ms.date: 02/15/2018
ms.keywords: IOCTL_NFCRM_SET_RADIO_STATE, IOCTL_NFCRM_SET_RADIO_STATE control, IOCTL_NFCRM_SET_RADIO_STATE control code [Near-Field Proximity Drivers], _IOCTL_NFCRM_SET_RADIO_STATE, nfcradiodev/IOCTL_NFCRM_SET_RADIO_STATE, nfpdrivers.ioctl_nfcrm_set_radio_state
ms.topic: ioctl
f1_keywords:
 - "nfcradiodev/IOCTL_NFCRM_SET_RADIO_STATE"
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
- IOCTL_NFCRM_SET_RADIO_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_NFCRM_SET_RADIO_STATE IOCTL


## -description


This IOCTL is used by the radio management application or service to set the radio power state of the proximity device. The MediaRadioOn field is used to indicate the request power state. When the proximity radio power state is disabled, the driver should disable the proximity device interfaces (GUID_DEVINTERFACE_NFP and GUID_DEVINTERFACE_SMARTCARD_READER interfaces) and disable the P2P and reader/writer modes of the device. If the proximity radio power state is enabled, the driver should enable the proximity device interfaces and enable P2P and reader/writer modes of the controller. For more information about optimizing power modes on this device, see <a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/nfc-power-management">NFC Power Management</a>.


## -ioctlparameters




### -input-buffer


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/nfcradiodev/ns-nfcradiodev-_nfcrm_set_radio_state"> NFCRM_SET_RADIO_STATE structure</a>



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
</table>
 


## -remarks



The <b>STATUS_INVALID_PARAMETER</b> return code is no longer required. A bug was discovered in Windows 10 build 10240, that Windows would send a non-null output parameter with this IOCTL. This bug was fixed in later versions of Windows. To simplify code, drivers can ignore the output parameters in all versions of Windows 10.



