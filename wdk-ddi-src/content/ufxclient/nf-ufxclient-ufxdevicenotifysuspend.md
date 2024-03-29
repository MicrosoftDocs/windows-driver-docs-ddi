---
UID: NF:ufxclient.UfxDeviceNotifySuspend
title: UfxDeviceNotifySuspend function (ufxclient.h)
description: Notifies UFX about a USB bus suspend event.
old-location: buses\ufxdevicenotifysuspend.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UfxDeviceNotifySuspend function"]
ms.keywords: UfxDeviceNotifySuspend, UfxDeviceNotifySuspend method [Buses], buses.ufxdevicenotifysuspend, ufxclient/UfxDeviceNotifySuspend
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
 - UfxDeviceNotifySuspend
 - ufxclient/UfxDeviceNotifySuspend
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ufxclient.h
api_name:
 - UfxDeviceNotifySuspend
---

# UfxDeviceNotifySuspend function


## -description

Notifies UFX about a USB bus suspend event.

## -parameters

### -param UfxDevice [in]


A handle to a UFX device object that the driver created by calling <a href="/windows-hardware/drivers/ddi/ufxclient/nf-ufxclient-ufxdevicecreate">UfxDeviceCreate</a>.

## -remarks

The client driver calls <b>UfxDeviceNotifySuspend</b> when it receives a bus suspend event. The default endpoint should be reset on a bus suspend.  The device should move to a low power mode.

The client driver typically calls <b>UfxDeviceNotifySuspend</b> from its <a href="/windows-hardware/drivers/ddi/wdfinterrupt/nc-wdfinterrupt-evt_wdf_interrupt_dpc">EvtInterruptDpc</a> callback function.  The following example shows how to handle a suspend event.


```
    case DeviceEventSuspend:
        if (!ControllerContext->Suspended) {
            ControllerContext->Suspended = TRUE;
            UfxDeviceNotifySuspend(ControllerContext->UfxDevice);
        }
        break;

```
