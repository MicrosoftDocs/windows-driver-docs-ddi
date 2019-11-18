---
UID: NF:mbbcx.MbbDeviceInitialize
title: MbbDeviceInitialize function (mbbcx.h)
description: The MbbDeviceInitialize method registers the client driver's MBB-specific callback functions.
tech.root: netvista
ms.assetid: 051cb7e8-4baf-46b2-99fd-43fc30dd49a9
ms.date: 06/28/2018
ms.topic: function
f1_keywords:
 - "mbbcx/MbbDeviceInitialize"
ms.keywords: MbbDeviceInitialize
req.header: mbbcx.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver:
req.lib: mbbcxstub.lib
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- LibDef
api_location: 
- mbbcxstub.lib
api_name: 
- MbbDeviceInitialize
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbDeviceInitialize function


## -description



The **MbbDeviceInitialize** method registers the client driver's MBB-specific callback functions.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param Config

A pointer to a client driver-allocated and initialized [**MBB_DEVICE_CONFIG**](ns-mbbcx-_mbb_device_config.md) structure.

## -returns

Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method may return an appropriate NTSTATUS error code.

This method might return failure in low resource situations.

## -remarks

The client driver must call this method after it calls [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md) from within [*EVT_WDF_DRIVER_DEVICE_ADD*](../wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add.md). 

For more information, see [Initialize the device](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#initialize-the-device).

## -see-also
