---
UID: NC:wdfdevice.EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX
title: EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX
author: windows-driver-content
description: A driver's EvtDeviceUsageNotificationEx event callback function determines whether a device can support a special file type.
old-location: wdf\evtdeviceusagenotificationex.htm
old-project: wdf
ms.assetid: A5C3E247-4883-4BFE-B36A-45AA989F36C9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviceusagenotificationex, EvtDeviceUsageNotificationEx callback function, EvtDeviceUsageNotificationEx, EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX, EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX, wdfdevice/EvtDeviceUsageNotificationEx, kmdf.evtdeviceusagenotificationex
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceUsageNotificationEx
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX callback


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceUsageNotificationEx</i> event callback function determines whether a device can support a special file type.


## -prototype


````
EVT_WDF_DEVICE_USAGE_NOTIFICATION_EX EvtDeviceUsageNotificationEx;

NTSTATUS EvtDeviceUsageNotificationEx(
  _In_ WDFDEVICE             Device,
  _In_ WDF_SPECIAL_FILE_TYPE NotificationType,
  _In_ BOOLEAN               IsInNotificationPath
)
{ ... }
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param NotificationType [in]

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_special_file_type.md">WDF_SPECIAL_FILE_TYPE</a>-typed value that identifies the type of special file that the system is storing on the specified device.


### -param IsInNotificationPath [in]

A Boolean value which, if <b>TRUE</b>, indicates that the system has starting using the special file and, if <b>FALSE</b>, indicates that the system has finished using the special file.


## -returns


If the driver determines that the device can support the special file, the <i>EvtDeviceUsageNotificationEx</i> callback function must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>.



## -remarks


If your driver must provide driver-specific handling of special files, you must provide either an <i>EvtDeviceUsageNotificationEx</i> or an <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_usage_notification.md">EvtDeviceUsageNotification</a> event callback function. Do not provide both callback functions.

To register an <i>EvtDeviceUsageNotificationEx</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver's <i>EvtDeviceUsageNotificationEx</i> callback function returns a failure status, the framework propagates failure to other stacks that it may have notified earlier.

For more information about special files, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.


