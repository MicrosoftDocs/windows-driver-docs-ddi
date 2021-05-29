---
UID: NC:hidspicx.EVT_HIDSPICX_RESETDEVICE
tech.root: hid
title: EVT_HIDSPICX_RESETDEVICE
ms.date: 
targetos: Windows
description: 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: hidspicx.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: WIN10_NEXT
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - hidspicx.h
api_name:
 - EVT_HIDSPICX_RESETDEVICE
f1_keywords:
 - EVT_HIDSPICX_RESETDEVICE
 - hidspicx/EVT_HIDSPICX_RESETDEVICE
dev_langs:
 - c++
---

## -description

The **EVT_HIDSPICX_RESETDEVICE** routine returns a NTSTATUS indicating whether the reset was successful or not.

## -parameters

### -param Device

WDF handle to the device object this method is being called for.

## -returns

NTSTATUS indicating whether the reset was successful or not. This method is not expected to fail at runtime, and may result in a failure of the device by HidSpiCx.

## -remarks

The client driver is expected to implement and provide a reset callback. The class extension will call this function only while the hardware is in a working state (post-D0Entry after Interrupts / DMA enabled, and pre-D0Exit before Interrupts / DMA disbaled), at passive IRQL.

The client driver shall synchronously reset the device, and return a status code indicating whether the physical reset was successful (*not* upon receipt of the reset response ??? which will be later provided to the class extension as an input report).

## -see-also

