---
UID: NF:ucmucsidevice.UcmUcsiDeviceInitInitialize
title: UcmUcsiDeviceInitInitialize function (ucmucsidevice.h)
tech.root: usbref
description: Intializes the **WDFDEVICE_INIT** provided by the framework.
ms.assetid: 83e766bc-b500-44d0-bc15-270d0cb3e31d
ms.date: 09/30/2018
ms.topic: function
ms.keywords: UcmUcsiDeviceInitInitialize
req.header: ucmucsidevice.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
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
- LibDef
api_location: 
- UcmUcsiCxStub.lib
api_name: 
- UcmUcsiDeviceInitialize
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UcmUcsiDeviceInitInitialize function


## -description

Intializes the [**WDFDEVICE_INIT**](https://msdn.microsoft.com/library/windows/hardware/ff546951) provided by the framework.

## -parameters

### -param DeviceInit
A pointer to a framework-allocated [**WDFDEVICE_INIT**](https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init) structure.

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, returns an appropriate [NTSTATUS](https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505) code.

## -remarks
The client driver must call this function after calling [**WdfDeviceInitSetPnpPowerEventCallbacks**](../wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md). This function initializes the UCSI extension (UcmUcsiCx) with the framework **WDFDEVICE_INIT** structure that contains pointers to PnP and power callback functions implemented by the client driver.

## -see-also
