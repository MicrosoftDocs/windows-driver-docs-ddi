---
UID: NF:ufxclient.UfxDeviceNotifyHardwareFailure
title: UfxDeviceNotifyHardwareFailure function (ufxclient.h)
description: Notifies UFX about a non-recoverable hardware failure in the controller.
old-location: buses\ufxdevicenotifyhardwarefailure.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UfxDeviceNotifyHardwareFailure function"]
ms.keywords: UfxDeviceNotifyHardwareFailure, UfxDeviceNotifyHardwareFailure method [Buses], buses.ufxdevicenotifyhardwarefailure, ufxclient/UfxDeviceNotifyHardwareFailure
req.header: ufxclient.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ufxstub.lib
req.dll: 
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - UfxDeviceNotifyHardwareFailure
 - ufxclient/UfxDeviceNotifyHardwareFailure
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxDeviceNotifyHardwareFailure
---

# UfxDeviceNotifyHardwareFailure function


## -description

Notifies UFX about a non-recoverable hardware failure in the controller.

## -parameters

### -param UfxDevice [in]


A handle to a UFX device object that the driver created by calling <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

### -param HardwareFailureContext [in, optional]


Optional pointer to a client driver-defined <a href="/windows-hardware/drivers/ddi/ufxbase/ns-ufxbase-_ufx_hardware_failure_context">UFX_HARDWARE_FAILURE_CONTEXT</a> structure containing controller-specific information about the hardware failure.

## -remarks

The client driver calls <b>UfxDeviceNotifyHardwareFailure</b> when the controller has entered a non-recoverable hardware failure (such as PHY lockup). UFX can try resetting the controller to see if the controller can be recovered. The following example shows the syntax for the call:


```
    UfxDeviceNotifyHardwareFailure(
        ControllerContext->UfxDevice,
        (PUFX_HARDWARE_FAILURE_CONTEXT) HardwareFailureContext);


```
