---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_ATTRIBUTE
title: IOCTL_SMARTCARD_SET_ATTRIBUTE (winsmcrd.h)
description: The IOCTL_SMARTCARD_SET_ATTRIBUTE control code sets an attribute and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED.
old-location: nfpdrivers\ioctl_smartcard_set_attribute.htm
tech.root: nfpdrivers
ms.date: 07/15/2022
keywords: ["IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL"]
ms.keywords: IOCTL_SMARTCARD_SET_ATTRIBUTE, IOCTL_SMARTCARD_SET_ATTRIBUTE control, IOCTL_SMARTCARD_SET_ATTRIBUTE control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_set_attribute, winsmcrd/IOCTL_SMARTCARD_SET_ATTRIBUTE
req.header: winsmcrd.h
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
 - IOCTL_SMARTCARD_SET_ATTRIBUTE
 - winsmcrd/IOCTL_SMARTCARD_SET_ATTRIBUTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsmcrd.h
api_name:
 - IOCTL_SMARTCARD_SET_ATTRIBUTE
---

# IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL

## -description

The **IOCTL_SMARTCARD_SET_ATTRIBUTE** control code sets various attributes in a smart card reader driver and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

(DWORD) contains the attribute identifier.

* **Irp->AssociatedIrp.SystemBuffer**
  Contains the tag and value to set.

* **Parameters.DeviceIoControl.InputBufferLength**
  Contains the length of the tag-length value (TLV) structure.

### -input-buffer-length

### -output-buffer

None.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Information** must be set to sizeof(ULONG).

**Irp->IoStatus.Status** is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| STATUS_SUCCESS            | The attribute has been set successfully. |
| STATUS_NOT_SUPPORTED      | The attribute is not supported. |
| STATUS_INVALID_PARAMETER  | The attribute to set is in the wrong format.
| STATUS_DEVICE_POWERED_OFF | The proximity radio control is off. |

## -see-also

[Near field communication (NFC) design guide](/windows-hardware/drivers/nfc/)

[Smart card design guide](/windows-hardware/drivers/nfc/design-guide-smart-card)
