---
UID: NF:poscx.PosCxReleaseDevice
title: PosCxReleaseDevice function (poscx.h)
description: PosCxReleaseDevice is called to release a device that was previously claimed with PosCxClaimDevice. Once the device is released, the next pending claim requester is promoted.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxReleaseDevice function"]
ms.keywords: PosCxReleaseDevice, PosCxReleaseDevice function, pos.poscxreleasedevice, poscx/PosCxReleaseDevice
req.header: poscx.h
req.include-header: Poscx.h
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
req.product: Windows 10 or later.
f1_keywords:
 - PosCxReleaseDevice
 - poscx/PosCxReleaseDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxReleaseDevice
---

## -description

PosCxReleaseDevice is called to release a device that was previously claimed with [PosCxClaimDevice](./nf-poscx-poscxclaimdevice.md). Once the device is released, the next pending claim requester is promoted.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param fileObject [in]

      A handle to a framework file object that identifies the caller.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The device was successfully released. |
| **STATUS_ACCESS_DENIED** | The calling thread is not the owner of the device. |
| **STATUS_DEVICE_NOT_READY** | The PosCx library was not successfully initialized. |
| **STATUS_INVALID_PARAMETER** | The specified *fileObject* is invalid. |

## -see-also

[PosCxClaimDevice](./nf-poscx-poscxclaimdevice.md)