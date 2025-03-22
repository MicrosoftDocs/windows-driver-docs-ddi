---
UID: NS:usbioctl._USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
tech.root: usbref
title: USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
ms.date: 01/29/2024
targetos: Windows
description: 
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: usbioctl.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION, *PUSB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - _USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - PUSB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
f1_keywords:
 - _USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - usbioctl/_USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - PUSB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - usbioctl/PUSB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
 - usbioctl/USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION
---

# USB_NODE_CONNECTION_SUPERSPEEDPLUS_INFORMATION structure (usbioctl.h)

## -description

## -struct-fields

### -field ConnectionIndex

The one based port number.

### -field Length

The length of this structure.

### -field RxSuperSpeedPlus

Current operating speed for receiving lanes.

### -field RxLaneCount

The zero-based number of receiving lanes. For actual lane count, add one.

### -field TxSuperSpeedPlus

Current operating speed for transmitting lanes.

### -field TxLaneCount

The zero-based number of transmitting lanes. For actual lane count, add one.

## -remarks

## -see-also

