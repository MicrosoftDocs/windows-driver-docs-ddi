---
UID: NE:ucmucsispec._UCSI_USB_OPERATION_ROLE
title: _UCSI_USB_OPERATION_ROLE (ucmucsispec.h)
tech.root: usbref
description: Used in the SET_UOR command. The SET_UOR command is used to set the USB operation role dictated by the OS Policy Manager (OPM), for the current connection.
ms.date: 05/01/2024
keywords: ["UCSI_USB_OPERATION_ROLE enumeration"]
ms.keywords: _UCSI_USB_OPERATION_ROLE, UCSI_USB_OPERATION_ROLE,
req.header: ucmucsispec.h
req.construct-type: enumeration
req.include-header: UcmUcsiCx.h
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.ddi-compliance: 
req.max-support: 
req.typenames: UCSI_USB_OPERATION_ROLE
targetos: Windows
ms.custom: RS5
f1_keywords:
 - _UCSI_USB_OPERATION_ROLE
 - ucmucsispec/_UCSI_USB_OPERATION_ROLE
 - UCSI_USB_OPERATION_ROLE
 - ucmucsispec/UCSI_USB_OPERATION_ROLE
api_name:
 - _UCSI_USB_OPERATION_ROLE
 - UCSI_USB_OPERATION_ROLE
---

# UCSI_USB_OPERATION_ROLE enumeration (ucmucsispec.h)



## -description

Used in the SET_UOR command. The SET_UOR command is used to set the USB operation role dictated by the OS Policy Manager (OPM), for the current connection.

## -enum-fields

### -field UcsiUsbOperationRoleDfp:0x1

The connector initiates swap to downstream-facing port (DFP), if not already operating in DFP mode.

### -field UcsiUsbOperationRoleUfp:0x2

The connector initiates swap to upstream-facing port (UFP), if not already operating in UFP mode.

### -field UcsiUsbOperationRoleAcceptSwap:0x4

The connector accepts USB operation role swap requests from the port partner. If this bit is cleared, connector rejects role swap requests from the port partner.

### -field UcsiUsbOperationRoleDfpAcceptSwap:0x5

This field combines the *UcsiUsbOperationRoleDfp* and *UcsiUsbOperationRoleAcceptSwap* values.

### -field UcsiUsbOperationRoleUfpAcceptSwap:0x6

This field combines the *UcsiUsbOperationRoleUfp* and *UcsiUsbOperationRoleAcceptSwap* values.

## -remarks

For more information, see section 4.5.9 in the [UCSI spec version 1.2](https://www.intel.com/content/www/us/en/products/docs/io/universal-serial-bus/usb-type-c-ucsi-spec.html).

## -see-also

- [UCSI spec version 1.2](https://www.intel.com/content/www/us/en/products/docs/io/universal-serial-bus/usb-type-c-ucsi-spec.html)
