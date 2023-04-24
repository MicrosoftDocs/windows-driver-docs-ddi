---
UID: NF:poscx.PosCxClaimDevice
title: PosCxClaimDevice function (poscx.h)
description: PosCxClaimDevice is called to claim a device for exclusive use. The caller should call PosCxReleaseDevice when the device is no longer needed.
tech.root: pos
ms.date: 03/07/2023
keywords: ["PosCxClaimDevice function"]
ms.keywords: PosCxClaimDevice, PosCxClaimDevice function, pos.poscxclaimdevice, poscx/PosCxClaimDevice
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
 - PosCxClaimDevice
 - poscx/PosCxClaimDevice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - poscx.h
api_name:
 - PosCxClaimDevice
---

## -description

PosCxClaimDevice is called to claim a device for exclusive use.

The caller should call [PosCxReleaseDevice](./nf-poscx-poscxreleasedevice.md) when the device is no longer needed.

If the device is already claimed, the caller must wait until access is granted.

## -parameters

### -param device [in]

A handle to a framework device object that represents the device.

### -param request [in]

A handle to a framework request object that represents the request. This request must come from a WDF IO queue.

## -returns

Possible return values are:

| Value | Description |
|---|---|
| **STATUS_SUCCESS** | The device was successfully claimed. |
| **STATUS_PENDING** | The claim request was queued. |
| **STATUS_DEVICE_NOT_READY** | The PosCx library was not successfully initialized. |
| **STATUS_ACCESS_DENIED** | The current owner has retained device ownership. |