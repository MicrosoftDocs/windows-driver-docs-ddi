---
UID: NF:wdm.IoRegisterPlugPlayNotification
title: IoRegisterPlugPlayNotification function
author: windows-driver-content
description: The IoRegisterPlugPlayNotification routine registers a Plug and Play (PnP) notification callback routine to be called when a PnP event of the specified category occurs.
old-location: kernel\ioregisterplugplaynotification.htm
old-project: kernel
ms.assetid: 06fd10ab-3478-4b01-b678-24944f17fa9d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: IoRegisterPlugPlayNotification, k104_2210e60c-f9ca-4848-8aab-7b01d2d2ffd7.xml, kernel.ioregisterplugplaynotification, wdm/IoRegisterPlugPlayNotification, IoRegisterPlugPlayNotification routine [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkPower, MarkPowerDown, MarkQueryRelations, MarkStartDevice, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRegisterPlugPlayNotification
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# IoRegisterPlugPlayNotification function


## -description


The <b>IoRegisterPlugPlayNotification</b> routine registers a Plug and Play (PnP) notification callback routine to be called when a PnP event of the specified category occurs.


## -syntax


````
NTSTATUS IoRegisterPlugPlayNotification(
  _In_     IO_NOTIFICATION_EVENT_CATEGORY        EventCategory,
  _In_     ULONG                                 EventCategoryFlags,
  _In_opt_ PVOID                                 EventCategoryData,
  _In_     PDRIVER_OBJECT                        DriverObject,
  _In_     PDRIVER_NOTIFICATION_CALLBACK_ROUTINE CallbackRoutine,
  _In_opt_ PVOID                                 Context,
  _Out_    PVOID                                 *NotificationEntry
);
````


## -parameters




### -param EventCategory [in]

The category of PnP event for which the callback routine is being registered. <i>EventCategory</i> must be one of the following: 




#### EventCategoryDeviceInterfaceChange

PnP events in this category include the arrival (enabling) of a new instance of a <a href="https://msdn.microsoft.com/C989D2D3-E8DE-4D64-86EE-3D3B3906390D">device interface class</a> (GUID_DEVICE_INTERFACE_ARRIVAL), or the removal (disabling) of an existing device interface instance (GUID_DEVICE_INTERFACE_REMOVAL).


#### EventCategoryHardwareProfileChange

PnP events in this category include query-change (GUID_HWPROFILE_QUERY_CHANGE), change-complete (GUID_HWPROFILE_CHANGE_COMPLETE), and change-cancel (GUID_HWPROFILE_CHANGE_CANCELLED) of a hardware profile.


#### EventCategoryTargetDeviceChange

PnP events in this category include events related to removing a device: the device's drivers received a query-remove IRP (GUID_TARGET_DEVICE_QUERY_REMOVE), the drivers completed a remove IRP (GUID_TARGET_DEVICE_REMOVE_COMPLETE), or the drivers received a cancel-remove IRP (GUID_TARGET_DEVICE_REMOVE_CANCELLED). This category is also used for custom notification events.


### -param EventCategoryFlags [in]

Flag bits that modify the registration operation. Possible values include:




#### PNPNOTIFY_DEVICE_INTERFACE_INCLUDE_EXISTING_INTERFACES

Only valid with an <i>EventCategory</i> of <b>EventCategoryDeviceInterfaceChange</b>. If set, the PnP manager calls the driver callback routine for each device interface instance that is currently registered and active and registers the callback routine for future arrivals or removals of device interface instances.


### -param EventCategoryData [in, optional]

A pointer to further information about the events for which <i>CallbackRoutine</i> is being registered. The information varies for different <i>EventCategory</i> values:
<ul>
<li>
When <i>EventCategory</i> is <b>EventCategoryDeviceInterfaceChange</b>, <i>EventCategoryData</i> must point to a GUID specifying a device interface class. <i>CallbackRoutine</i> will be called when an interface of that class is enabled or removed.

</li>
<li>
When <i>EventCategory</i> is <b>EventCategoryHardwareProfileChange</b>, <i>EventCategoryData</i> must be <b>NULL</b>.

</li>
<li>
When <i>EventCategory</i> is <b>EventCategoryTargetDeviceChange</b>, <i>EventCategoryData</i> must point to the file object for which PnP notification is requested.

</li>
</ul>

### -param DriverObject [in]

A pointer to the caller's driver object.

To ensure that the driver remains loaded while it is registered for PnP notification, this call increments the reference count on <i>DriverObject</i>. The PnP manager decrements the reference count when this registration is removed.


### -param CallbackRoutine [in]

A pointer to the PnP notification callback routine to be called when the specified PnP event occurs.

The function prototype for this callback routine is defined as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef NTSTATUS 
  DRIVER_NOTIFICATION_CALLBACK_ROUTINE(
    _In_ PVOID NotificationStructure,
    _Inout_opt_ PVOID Context
    );</pre>
</td>
</tr>
</table></span></div>The callback routine's <i>NotificationStructure</i> is specific to the <i>EventCategory</i> value, as shown in the following table.
<table>
<tr>
<th>Event category</th>
<th>Notification structure</th>
</tr>
<tr>
<td>
<b>EventCategoryDeviceInterfaceChange</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>


</td>
</tr>
<tr>
<td>
<b>EventCategoryHardwareProfileChange</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>


</td>
</tr>
<tr>
<td>
<b>EventCategoryTargetDeviceChange</b>

</td>
<td>

<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>


</td>
</tr>
</table> 

The callback routine's <i>Context</i> parameter contains the context data the driver supplied during registration.

For information about including a function declaration for the callback routine  that meets the requirements of <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), see Examples.

The PnP manager calls driver callback routines at IRQL = PASSIVE_LEVEL.


### -param Context [in, optional]

A pointer to a caller-allocated buffer containing context that the PnP manager passes to the callback routine.


### -param NotificationEntry [out]

A pointer to an opaque value returned by this call that identifies the registration. Pass this value to the <a href="..\wdm\nf-wdm-iounregisterplugplaynotificationex.md">IoUnregisterPlugPlayNotificationEx</a> routine to remove the registration. (In versions of Windows before Windows 7, call the <a href="..\wdm\nf-wdm-iounregisterplugplaynotification.md">IoUnregisterPlugPlayNotification</a> routine instead of <b>IoUnregisterPlugPlayNotificationEx</b>.)


## -returns


<b>IoRegisterPlugPlayNotification</b> returns STATUS_SUCCESS or an appropriate error status.



## -remarks


A driver registers for an event category. Each category includes one or more types of PnP events.

A driver can register different callback routines for different event categories or can register a single callback routine. A single callback routine can cast the <i>NotificationStructure</i> to a <a href="..\wdm\ns-wdm-_plugplay_notification_header.md">PLUGPLAY_NOTIFICATION_HEADER</a> and use the <b>Event</b> field to determine the exact type of the notification structure.
<div class="alert"><b>Warning</b>  If the caller specifies PNPNOTIFY_DEVICE_INTERFACE_INCLUDE_EXISTING_INTERFACES, the operating system might call the PnP notification callback routine twice for a single <b>EventCategoryDeviceInterfaceChange</b> event for an existing interface. You can safely ignore the second call to the callback. The operating system will not call the callback more than twice for a single event.</div><div> </div>PnP notification callback routines should complete their tasks as quickly as possible and return control to the PnP manager, to prevent delays in notifying other drivers and applications that have registered for the event.

The PnP manager does not take out a reference on the file object when a driver registers for notification of an <b>EventCategoryTargetDeviceChange</b> event. If the driver's PnP notification callback routine requires access to the file object, the driver should take out an extra reference on the file object before calling <b>IoRegisterPlugPlayNotification</b>.

Typically, Kernel-Mode Driver Framework (KMDF) drivers should call <b>IoRegisterPlugPlayNotification</b> from their <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a> callback function, and should call <b>IoUnregisterPlugPlayNotification</b> from their <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a> callback function. These drivers should <u>not</u> call <b>IoRegisterPlugPlayNotification</b> from their <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function; otherwise, the PnP notification callback routine might be called before the driver stack is started by PnP, in which case the driver will not be prepared to handle the notification.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565480">Using PnP Notification</a>.



## -see-also

<a href="..\wdm\nf-wdm-iounregisterplugplaynotificationex.md">IoUnregisterPlugPlayNotificationEx</a>

<a href="..\wdm\nf-wdm-iounregisterplugplaynotification.md">IoUnregisterPlugPlayNotification</a>

<a href="..\wdm\ns-wdm-_target_device_removal_notification.md">TARGET_DEVICE_REMOVAL_NOTIFICATION</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdm\ns-wdm-_device_interface_change_notification.md">DEVICE_INTERFACE_CHANGE_NOTIFICATION</a>

<a href="..\wdm\ns-wdm-_hwprofile_change_notification.md">HWPROFILE_CHANGE_NOTIFICATION</a>

<a href="..\wdm\ns-wdm-_plugplay_notification_header.md">PLUGPLAY_NOTIFICATION_HEADER</a>

<a href="..\wdm\ns-wdm-_target_device_custom_notification.md">TARGET_DEVICE_CUSTOM_NOTIFICATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRegisterPlugPlayNotification routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

