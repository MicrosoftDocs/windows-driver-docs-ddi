---
UID: NC:wdfcontrol.EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
title: EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION (wdfcontrol.h)
description: A driver's EvtDeviceShutdownNotification event callback function notifies the driver that the system is about to lose its power.
old-location: wdf\evtdeviceshutdownnotification.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION callback function"]
ms.keywords: DFDeviceObjectControllerDevObjRef_d7dab025-aa6d-4f66-a0cb-3784b3bc7b1c.xml, EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION, EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION callback, EvtDeviceShutdownNotification, EvtDeviceShutdownNotification callback function, kmdf.evtdeviceshutdownnotification, wdf.evtdeviceshutdownnotification, wdfcontrol/EvtDeviceShutdownNotification
req.header: wdfcontrol.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
 - wdfcontrol/EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfControl.h
api_name:
 - EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION
---

# EVT_WDF_DEVICE_SHUTDOWN_NOTIFICATION callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtDeviceShutdownNotification</i> event callback function notifies the driver that the system is about to lose its power.

## -parameters

### -param Device 

[in]
A handle to a framework device object that the driver initialized by calling <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>.

## -remarks

To register an <i>EvtDeviceShutdownNotification</i> event callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification">WdfControlDeviceInitSetShutdownNotification</a>. Only drivers that create control device objects can register this callback function.

The framework calls a driver's <i>EvtDeviceShutdownNotification</i> event callback function if the user is about to turn off the computer, or if the computer suddenly loses its power and an emergency power supply, such as an uninterruptible power supply (UPS), is available to safely turn off the computer.

For more information about control device objects and the <i>EvtDeviceShutdownNotification</i> callback function see <a href="/windows-hardware/drivers/wdf/using-control-device-objects">Using Control Device Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitallocate">WdfControlDeviceInitAllocate</a>



<a href="/windows-hardware/drivers/ddi/wdfcontrol/nf-wdfcontrol-wdfcontroldeviceinitsetshutdownnotification">WdfControlDeviceInitSetShutdownNotification</a>

