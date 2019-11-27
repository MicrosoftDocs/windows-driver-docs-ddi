---
UID: NF:storport.StorPortMarkDeviceFailedEx
title: StorPortMarkDeviceFailedEx function
author: windows-driver-content
description: The StorPortMarkDeviceFailedEx routine marks a device with failed status and provides data that might be needed for diagnosis.
tech.root: storage
ms.assetid: b3a300c1-7c14-4c6c-90c6-2fd8b89a1de8
ms.author: windowsdriverdev
ms.date: 12/15/2019
ms.topic: function
f1_keywords:
 - "storport/StorPortMarkDeviceFailedEx"
ms.keywords: StorPortMarkDeviceFailedEx
req.header: storport.h
req.include-header:
req.target-type:
req.target-min-winverclnt: The next version of Windows 10
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
topic_type: 
- apiref
api_type: 
- 
api_location: 
- 
api_name: 
- StorPortMarkDeviceFailedEx
product: 
- Windows
targetos: Windows

---

# StorPortMarkDeviceFailedEx function

## -description

The **StorPortMarkDeviceFailedEx** routine marks a device with failed status and provides data that might be needed for diagnosis.

## -parameters

### -param HwDeviceExtension

Pointer to the hardware device extension for the host bus adapter (HBA).

### -param StorAddress

Storage unit device address. This parameter is NULL for adapter devices.

### -param Flags

Indicates the behavior being requested by the miniport. *Flags* can be set to one of the following values.

| Flag | Meaning |
| ---- | ------- |
| STORPORT_MARK_DEVICE_FAILED_FLAG_REMOVE_DEVICE | Remove the failed device. |
| STORPORT_MARK_DEVICE_FAILED_FLAG_PREDICTED_FAILURE | Indicates that this is a predicted device failure. |

### -param FaultCode

Miniport-specific fault code.

### -param FaultDescription

Human-readable string that describes the fault.

### -param AdditionalDataSize

Size in bytes of the buffer that *AdditionalData* points to.

### -param AdditionalData

Pointer to a buffer containing additional data associated with the fault condition.

### -param CriticalDataSize

Size in bytes of the buffer that *CriticalData* points to.

### -param CriticalData

Pointer to a buffer containing critical data associated with the fault condition.

## - returns

**StorPortMarkDeviceFailedEx** returns a valid STOR_STATUS code.

## -remarks

A miniport driver can call this function to mark a failed device or to indicate that the device has potentially failed. 

If no flags are set in *Flags*, Storport will only log the event.

The PnP manager will send an IRP to query the failed device's PnP state. If *Flags* is set to STORPORT_MARK_DEVICE_FAILED_FLAG_REMOVE_DEVICE and not set to STORPORT_MARK_DEVICE_FAILED_FLAG_PREDICTED_FAILURE, the PnP manager will then try to remove the failed device.

## -see-also

[IoInvalidateDeviceState](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioinvalidatedevicestate)

[**StorPortMarkDeviceFailed**](https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportmarkdevicefailed)
