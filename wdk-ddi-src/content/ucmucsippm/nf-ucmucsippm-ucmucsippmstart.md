---
UID: NF:ucmucsippm.UcmUcsiPpmStart
title: UcmUcsiPpmStart function (ucmucsippm.h)
tech.root: usbref
description: Instructs the class extension to start sending requests to the client driver.
ms.assetid: b0899727-573a-4cd6-b1b4-3ca6b682bffa
ms.date: 09/30/2018
keywords: ["UcmUcsiPpmStart function"]
f1_keywords:
 - "ucmucsippm/UcmUcsiPpmStart"
ms.keywords: UcmUcsiPpmStart
req.header: Ucmucsippm.h
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
- UcmUcsiPpmStart
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# UcmUcsiPpmStart function


## -description

Instructs the UcmUcsiCx class extension to start sending requests to the client driver.

## -parameters

### -param PpmObject [in]
A handle to a Platform Policy Manager (PPM) object that the client driver received in the previous call to [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md).

## -returns
Returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return an appropriate [NTSTATUS](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values) value.


## -remarks

**UcmUcsiPpmStart** indicates that the client driver is now ready to receive request from the class extension. Upon this call, the class extension starts OS Policy Manager (OPM) and Command Handler state machines.

The client driver must call **UcmUcsiPpmStart** after it had called UcmUcsiPpmStop for error recovery.  

This DDI starts the operations that the class extension needs to perform to initialize the OPM and Command Handler state machines. The client driver must call **UcmUcsiPpmStart** to notify UcmUcsiCx that the driver is ready to receive the IOCTL requests. We recommend that you make this call either from the [**EVT_WDF_DEVICE_PREPARE_HARDWARE**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware) callback function, or after the system calls this callback.

Attempting to start the PPM after it has already started leads to an error condition.  

After the client calls **UcmUcsiPpmStart**, the class extension sends a number of commands to the PPM firmware in order to get PPM and connector capabilities and their statuses. Due to a high number interactions with the firmware, we strongly recommend UcmUcsiCx client implementors to call this DDI once during startup and not on resume from a low power state e.g. D0Entry callback specially when the client implements S0 idling.

## -see-also
