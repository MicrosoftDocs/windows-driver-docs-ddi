---
UID: NI:nfpdev.IOCTL_NFP_ENABLE
title: IOCTL_NFP_ENABLE (nfpdev.h)
description: The client sends the IOCTL_NFP_ENABLE request to re-enable previously disabled subscriptions, publications, and presence events.
old-location: nfpdrivers\ioctl_nfp_enable.htm
tech.root: nfpdrivers
ms.assetid: 25D4C7BB-782D-4BDB-9E07-F152E3705705
ms.date: 02/15/2018
keywords: ["IOCTL_NFP_ENABLE IOCTL"]
ms.keywords: IOCTL_NFP_ENABLE, IOCTL_NFP_ENABLE control, IOCTL_NFP_ENABLE control code [Near-Field Proximity Drivers], _IOCTL_NFP_ENABLE, nfpdev/IOCTL_NFP_ENABLE, nfpdrivers.ioctl_nfp_enable
req.header: nfpdev.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
 - IOCTL_NFP_ENABLE
 - nfpdev/IOCTL_NFP_ENABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - nfpdev.h
api_name:
 - IOCTL_NFP_ENABLE
---

# IOCTL_NFP_ENABLE IOCTL


## -description

The client sends the <b>IOCTL_NFP_ENABLE</b> request to re-enable previously disabled subscriptions, publications, and presence events.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

The following are required actions when using this IOCTL:<ul>
<li>
	When this IOCTL is received the driver MUST mark the file handle as “Enabled”.

</li>
<li>
	If the file handle is already marked “Enabled” the driver MUST complete the IOCTL with STATUS_INVALID_DEVICE_STATE.

</li>
<li>
If a device is currently proximate when this IOCTL is successfully completed, then the message data (along with its type) MUST be transmitted (only once) to the proximate device.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/ddi/nfpdev/ni-nfpdev-ioctl_nfp_disable">IOCTL_NFP_DISABLE</a>



<a href="/windows-hardware/drivers/nfc/">Near field communication (NFC) overall design guide</a>



<a href="/windows-hardware/drivers/nfc/nfp-design-guide">Near field proximity design guide (Tap and Do, NFP provider model, driver requirements)</a>