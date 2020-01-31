---
UID: NI:pointofservicedriverinterface.IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE
title: IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE (pointofservicedriverinterface.h)
description: The I/O control function claims the device for exclusive access.
old-location: pos\ioctl_point_of_service_claim_device.htm
tech.root: pos
ms.assetid: e9dfa630-d3ac-4228-ae2a-02ff5a0fd558
ms.date: 02/23/2018
ms.keywords: IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE, IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE control, IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE control code, pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE, pos.ioctl_point_of_service_claim_device
f1_keywords:
 - "pointofservicedriverinterface/IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE"
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
- pointofservicedriverinterface.h
api_name:
- IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_POINT_OF_SERVICE_CLAIM_DEVICE IOCTL


## -description


The I/O control function claims the device for exclusive access.


## -ioctlparameters




### -input-buffer

Not used with this operation; set to <b>NULL</b>.


### -input-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -output-buffer

Not used with this operation; set to <b>NULL</b>.


### -output-buffer-length

Not used with this operation; set to <b>0</b> (zero).


### -in-out-buffer








### -inout-buffer-length








### -status-block

Returns <b>TRUE</b> if successful; otherwise, returns <b>FALSE</b>.

## -remarks

To get extended error information, call <a href="https://go.microsoft.com/fwlink/p/?LinkId=316871">GetLastError</a>. The following list shows common error values:

- STATUS_ACCESS_DENIED: The claim could not be taken from the current claim owner.

- STATUS_DEVICE_NOT_READY: The POS library is not initialized.

- STATUS_PENDING: The claim request was queued.

This IOCTL is handled by the PosCx library. The driver writer does not need to handle this IOCTL. Instead, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/poscx/nf-poscx-poscxclaimdevice">PosCxClaimDevice</a>. If the POS device is already claimed by another client, then the POS device driver is responsible for notifying the claim owner using a <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/dn790033(v=vs.85)">ReleaseDeviceRequested</a> event and waiting for the claim owner to retain its claim within 50 milliseconds. If the claim is not reaffirmed, then the current claim owner's claim is automatically revoked and granted to the challenging client. 
