---
UID: NI:sidebandaudio.IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
title: IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES (sidebandaudio.h)
description: "The IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL gets the sidetone volume property values of the sideband specified audio endpoint"
ms.date: 07/14/2023
keywords: ["IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL"]
req.header: sidebandaudio.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.max-support: 
targetos: Windows
tech.root: audio
ms.custom: RS5
f1_keywords:
 - IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
 - sidebandaudio/IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - sidebandaudio.h
api_name:
 - IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES
---

# IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES IOCTL

## -description

The **IOCTL_SBAUD_GET_SIDETONE_VOLUMEPROPERTYVALUES** IOCTL gets the sidetone volume property values of the sideband specified audio endpoint.

This control code is used by an audio driver when cooperating with the audio class drivers to operate a sideband connection.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

(Information pending)

### -input-buffer-length

### -output-buffer

[KSPROPERTY_DESCRIPTION](../ks/ns-ks-ksproperty_description.md) information that describes the sidetone value properties.

(Information pending)

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a NTSTATUS code. 
For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -remarks

## -requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | sidebandaudio.h |

## -see-also

[Introduction to I/O Control Codes](/windows-hardware/drivers/kernel/introduction-to-i-o-control-codes)

[sidebandaudio.h](index.md)