---
UID: NF:ucmucsippm.UcmUcsiPpmStop
title: UcmUcsiPpmStop function (ucmucsippm.h)
tech.root: usbref
description: Instructs the class extension to stop sending requests to the client driver.
ms.assetid: 851fee56-96fc-4ec0-b9e6-7933463eac61
ms.date: 09/30/2018
f1_keywords:
 - "ucmucsippm/UcmUcsiPpmStop"
ms.keywords: UcmUcsiPpmStop
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib: UcmUcsiCxStub.lib
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
- UcmUcsiCxStub.lib
api_name: 
- UcmUcsiPpmStop
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# UcmUcsiPpmStop function


## -description

Instructs the UcmUcsiCx class extension to stop sending requests to the client driver.

## -parameters

### -param PpmObject [in]
A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md).

## -remarks

**UcmUcsiPpmStop** indicates that the client driver is no longer ready to receive requests from the class extension. The class extension guarantees that there will not be any requests made to the client after this call returns. The driver should call this DDI when it encounters a fault and wants the class extension to stop sending PPM requests. After the call completes, the driver should start the PPM again using [**UcmUcsiPpmStart**](nf-ucmucsippm-ucmucsippmstart.md).

The client driver is expected to call this DDI on driver unload. This call indicates the class extension to start tearing down its internal state machines. It is recommended that the client calls **UcmUcsiPpmStop** from its EVT_WDF_DEVICE_RELEASE_HARDWARE callback.

Because **UcmUcsiPpmStop** relies on sending UCSI commands to PPM over the power-managed WDFQUEUE provided by the client driver, an attempt to call this function from [EVT_WDF_DEVICE_D0_EXIT](../wdfdevice/nc-wdfdevice-evt_wdf_device_d0_exit.md) callback results in a failure. That is because at this time, the dispatch gates for the queue are closed.

After the **UcmUcsiPpmStop** returns, [**UcmUcsiPpmStart**](nf-ucmucsippm-ucmucsippmstart.md) can be called to start the PPM again.  

## -see-also
