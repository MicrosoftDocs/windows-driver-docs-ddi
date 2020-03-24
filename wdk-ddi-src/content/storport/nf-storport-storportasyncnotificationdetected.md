---
UID: NF:storport.StorPortAsyncNotificationDetected
title: StorPortAsyncNotificationDetected function (storport.h)
description: A storage miniport driver calls StorPortAsyncNotificationDetected to notify the Storport driver of a storage device status change event.
old-location: storage\storportasyncnotificationdetected.htm
tech.root: storage
ms.assetid: 558F652C-6D1A-4BAF-9C2C-3F4FE24651D2
ms.date: 03/29/2018
keywords: ["StorPortAsyncNotificationDetected function"]
ms.keywords: RAID_ASYNC_NOTIFY_FLAG_DEVICE_OPERATION, RAID_ASYNC_NOTIFY_FLAG_DEVICE_STATUS, RAID_ASYNC_NOTIFY_FLAG_MEDIA_STATUS, StorPortAsyncNotificationDetected, StorPortAsyncNotificationDetected routine [Storage Devices], storage.storportasyncnotificationdetected, storport/StorPortAsyncNotificationDetected
f1_keywords:
 - "storport/StorPortAsyncNotificationDetected"
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: 
req.dll: 
req.irql: Any
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- StorPortAsyncNotificationDetected
product:
- Windows
targetos: Windows
req.typenames: 
---

# StorPortAsyncNotificationDetected function


## -description


A storage miniport driver calls <b>StorPortAsyncNotificationDetected</b> to  notify the Storport driver of a storage device status change event.

The notification is queued as a work item for deferred processing at DISPATCH_LEVEL or lower IRQL.


## -parameters




### -param HwDeviceExtension [in]

A pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the mapped access ranges for the HBA. This area is available to the miniport driver immediately after the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nf-storport-storportinitialize">StorPortInitialize</a>. The port driver frees this memory when it removes the device.


### -param Address

The address of the storage device with a status change event.


### -param Flags

The status notifications to indicate to Storport.


The Flags parameter contains a bitwise OR combination of status notifications. All status values can be set with the single <b>RAID_ASYNC_NOTIFY_SUPPORTED_FLAGS</b> value.



<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="RAID_ASYNC_NOTIFY_FLAG_MEDIA_STATUS"></a><a id="raid_async_notify_flag_media_status"></a><dl>
<dt><b>RAID_ASYNC_NOTIFY_FLAG_MEDIA_STATUS</b></dt>
</dl>
</td>
<td width="60%">
Notify Storport that a media change occurred.

</td>
</tr>
<tr>
<td width="40%"><a id="RAID_ASYNC_NOTIFY_FLAG_DEVICE_STATUS"></a><a id="raid_async_notify_flag_device_status"></a><dl>
<dt><b>RAID_ASYNC_NOTIFY_FLAG_DEVICE_STATUS</b></dt>
</dl>
</td>
<td width="60%">
Notify Storport that the functional status of the storage device has changed.

</td>
</tr>
<tr>
<td width="40%"><a id="RAID_ASYNC_NOTIFY_FLAG_DEVICE_OPERATION"></a><a id="raid_async_notify_flag_device_operation"></a><dl>
<dt><b>RAID_ASYNC_NOTIFY_FLAG_DEVICE_OPERATION</b></dt>
</dl>
</td>
<td width="60%">
Notify Storport that an operational role of the storage device has changed.

</td>
</tr>
</table>
 


## -returns



A status value indicating the result of the notification. This can be one of these values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The state change notification is scheduled for processing.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The address type invalid.

-or-

<i>HwDeviceExtension</i> is <b>NULL</b>.

-or-

<i>Flags</i> contains an undefined value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The storage device unit cannot be found at <i>address</i>.

-or-

The storage device does not support asynchronous notifications.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STOR_STATUS_BUSY</b></dt>
</dl>
</td>
<td width="60%">
A prior notification is in process and this one cannot be scheduled.

</td>
</tr>
</table>
 




## -remarks



A miniport can detect status events in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/nc-storport-hw_interrupt">HwStorInterrupt</a> routine and call <b>StorPortAsyncNotificationDetected</b> to queue and process the status change notification later at a lower IRQL. 

When processed by Storport, the status event notification is forwarded to the storage class driver to initiate any necessary system response actions.

If the <i>Flags</i> parameter is 0, Storport will indicate all status values in its notification to the storage class driver.



