---
UID: NC:wdfdevice.EVT_WDF_DEVICE_USAGE_NOTIFICATION
title: EVT_WDF_DEVICE_USAGE_NOTIFICATION (wdfdevice.h)
description: A driver's EvtDeviceUsageNotification event callback function informs the driver when a device is being used for special files.
old-location: wdf\evtdeviceusagenotification.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_USAGE_NOTIFICATION callback function"]
ms.keywords: DFDeviceObjectGeneralRef_bbf01697-e3d0-4711-aa7f-c53bfd205ea7.xml, EVT_WDF_DEVICE_USAGE_NOTIFICATION, EVT_WDF_DEVICE_USAGE_NOTIFICATION callback, EvtDeviceUsageNotification, EvtDeviceUsageNotification callback function, kmdf.evtdeviceusagenotification, wdf.evtdeviceusagenotification, wdfdevice/EvtDeviceUsageNotification
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
 - EVT_WDF_DEVICE_USAGE_NOTIFICATION
 - wdfdevice/EVT_WDF_DEVICE_USAGE_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceUsageNotification
---

# EVT_WDF_DEVICE_USAGE_NOTIFICATION callback function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceUsageNotification</i> event callback function informs the driver when a device is being used for special files.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param NotificationType 

[in]
A <a href="/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">WDF_SPECIAL_FILE_TYPE</a>-typed value that identifies the type of special file that the system is storing on the specified device.

### -param IsInNotificationPath 

[in]
A Boolean value which, if <b>TRUE</b>, indicates that the system has starting using the special file and, if <b>FALSE</b>, indicate that the system as finished using the special file.

## -remarks

To register an <i>EvtDeviceUsageNotification</i> callback function, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

Your driver must provide an <i>EvtDeviceUsageNotification</i> callback function only if must provide driver-specific handling of special files. 

For more information about special files, see <a href="/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.
