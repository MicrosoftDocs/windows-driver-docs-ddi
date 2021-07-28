---
UID: NC:hidspicx.EVT_HIDSPICX_RESETDEVICE
tech.root: hid
title: EVT_HIDSPICX_RESETDEVICE
ms.date: 06/14/2021
targetos: Windows
description: "Learn more about: EVT_HIDSPICX_RESETDEVICE"
prerelease: false
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
req.target-min-winverclnt: Windows 11
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

The **EVT_HIDSPICX_RESETDEVICE** callback function is implemented by the client driver to respond to requests to reset the device.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

## -returns

[**NTSTATUS**](/windows-hardware/drivers/kernel/using-ntstatus-values) value indicating whether the reset was successful or not.

## -remarks

The class extension will call this function only while the hardware is in a working state, at passive IRQL.

The client driver synchronously resets the device and returns a status code indicating whether the reset was successful.

## -see-also
