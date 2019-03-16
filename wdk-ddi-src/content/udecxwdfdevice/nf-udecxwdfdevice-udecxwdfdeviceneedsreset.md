---
UID: NF:udecxwdfdevice.UdecxWdfDeviceNeedsReset
title: UdecxWdfDeviceNeedsReset function (udecxwdfdevice.h)
description: Informs the USB device emulation class extension (UdeCx) that the device needs a reset operation.
ms.assetid: 92e5253f-4209-4501-bd25-e560e9e39f61
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UdecxWdfDeviceNeedsReset
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: Udecxstub.lib
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
- Udecxstub.lib
api_name: 
- UdecxWdfDeviceNeedsReset
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UdecxWdfDeviceNeedsReset function


## -description

Informs the USB device emulation class extension (UdeCx) that the device needs a reset operation.

## -parameters

### -param UdeWdfDevice
[In] A handle to a framework device object that represents the a USB device. The client driver initialized this object in the previous call to [**UdecxWdfDeviceAddUsbDeviceEmulation**](../udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md).

### -param ResetType
[In] A [**UDECX_WDF_DEVICE_RESET_TYPE**](ne-udecxwdfdevice-_udecx_wdf_device_reset_type.md)-type value that indicates the type of reset.

## -returns
The function returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) error code.

## -remarks
If an existing reset operation is in progress, the function fails with a STATUS_DEVICE_BUSY error.


## -see-also
[**UDECX_WDF_DEVICE_RESET_TYPE**](ne-udecxwdfdevice-_udecx_wdf_device_reset_type.md)
