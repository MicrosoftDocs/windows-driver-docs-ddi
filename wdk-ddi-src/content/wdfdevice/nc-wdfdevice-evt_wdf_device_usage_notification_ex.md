---
UID: NC:wdfdevice.EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX
title: EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX (wdfdevice.h)
description: A driver's EvtDeviceUsageNotificationEx event callback function determines whether a device can support a special file type.
old-location: wdf\evtdeviceusagenotificationex.htm
tech.root: wdf
ms.assetid: A5C3E247-4883-4BFE-B36A-45AA989F36C9
ms.date: 02/26/2018
keywords: ["EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback function"]
ms.keywords: EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX, EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback, EvtDeviceUsageNotificationEx, EvtDeviceUsageNotificationEx callback function, kmdf.evtdeviceusagenotificationex, wdf.evtdeviceusagenotificationex, wdfdevice/EvtDeviceUsageNotificationEx
f1_keywords:
 - "wdfdevice/EvtDeviceUsageNotificationEx"
 - "EvtDeviceUsageNotificationEx"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceUsageNotificationEx
targetos: Windows
req.typenames: 
---

# EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

A driver's <i>EvtDeviceUsageNotificationEx</i> event callback function determines whether a device can support a special file type.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_special_file_type">WDF_SPECIAL_FILE_TYPE</a>-typed value that identifies the type of special file that the system is storing on the specified device.


### -param IsInNotificationPath [in]

A Boolean value which, if <b>TRUE</b>, indicates that the system has starting using the special file and, if <b>FALSE</b>, indicates that the system has finished using the special file.


## -returns



If the driver determines that the device can support the special file, the <i>EvtDeviceUsageNotificationEx</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.




## -remarks



If your driver must provide driver-specific handling of special files, you must provide either an <i>EvtDeviceUsageNotificationEx</i> or an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_usage_notification">EvtDeviceUsageNotification</a> event callback function. Do not provide both callback functions.

To register an <i>EvtDeviceUsageNotificationEx</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver's <i>EvtDeviceUsageNotificationEx</i> callback function returns a failure status, the framework propagates failure to other stacks that it may have notified earlier.

For more information about special files, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-special-files">Supporting Special Files</a>.




