---
UID: NF:mbbcx.MbbDeviceSetMbimParameters
title: MbbDeviceSetMbimParameters function (mbbcx.h)
description: The client driver calls the MbbDeviceSetMbimParameters method to report its MBIM-specification related parameters.
tech.root: netvista
ms.assetid: 87c11c92-f859-4b52-8aa0-7fe461cefc4c
ms.date: 06/29/2018
keywords: ["MbbDeviceSetMbimParameters function"]
f1_keywords:
 - "mbbcx/MbbDeviceSetMbimParameters"
 - "MbbDeviceSetMbimParameters"
ms.keywords: MbbDeviceSetMbimParameters
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
- MbbDeviceSetMbimParameters
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# MbbDeviceSetMbimParameters function


## -description



The client driver calls the **MbbDeviceSetMbimParameters** method to report its MBIM-specification related parameters.

## -parameters

### -param Device

A handle to a framework device object the client driver obtained from a previous call to [**WdfDeviceCreate**](../wdfdevice/nf-wdfdevice-wdfdevicecreate.md).

### -param MbimParameters

A pointer to a client driver-allocated and initialized [**MBB_DEVICE_MBIM_PARAMETERS**](ns-mbbcx-_mbb_device_mbim_parameters.md) structure.

## -remarks

The client driver typically calls this method from within [*EVT_DEVICE_PREPARE_HARDWARE*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md). 

For more information, see [Initialize the device](https://docs.microsoft.com/windows-hardware/drivers/netcx/writing-an-mbbcx-client-driver#initialize-the-device).

## -see-also
