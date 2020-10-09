---
UID: NF:storport.StorPortMarkDeviceFailed
title: StorPortMarkDeviceFailed function
description: The StorPortMarkDeviceFailed routine marks a device with failed status.
tech.root: storage
ms.assetid: 91951a88-18ba-4ddc-b8e0-d789f179fa1f
ms.date: 03/19/2019
keywords: ["StorPortMarkDeviceFailed function"]
ms.keywords: StorPortMarkDeviceFailed
req.header: storport.h
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
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - StorPortMarkDeviceFailed
 - storport/StorPortMarkDeviceFailed
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - storport.h
api_name:
 - StorPortMarkDeviceFailed
product:
 - Windows
dev_langs:
 - c++
---

# StorPortMarkDeviceFailed function


## -description

The **StorPortMarkDeviceFailed** routine marks a device with failed status. See also [**StorPortMarkDeviceFailedEx**](./nf-storport-storportmarkdevicefailedex.md).

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param StorAddress

Storage unit device address. This parameter is NULL for adapter devices.

### -param Flags

Set to STORPORT_MARK_DEVICE_FAILED_FLAG_REMOVE_DEVICE to remove the failed device.

### -param FailReason

String that specifies the reason for the device failure along with other details.

## -remarks

A miniport driver can call this function to mark a failed device. If STORPORT_MARK_DEVICE_FAILED_FLAG_REMOVE_DEVICE is not set in *Flags*, Storport will only log the event.

The PnP manager will send an IRP to query the failed device's PnP state. If *Flags* is set to STORPORT_MARK_DEVICE_FAILED_FLAG_REMOVE_DEVICE, the PnP manager will then try to remove the failed device.

## -see-also

[**IoInvalidateDeviceState**](../wdm/nf-wdm-ioinvalidatedevicestate.md)

[**StorPortMarkDeviceFailedEx**](./nf-storport-storportmarkdevicefailedex.md)