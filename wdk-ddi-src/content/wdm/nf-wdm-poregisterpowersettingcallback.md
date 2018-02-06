---
UID: NF:wdm.PoRegisterPowerSettingCallback
title: PoRegisterPowerSettingCallback function
author: windows-driver-content
description: The PoRegisterPowerSettingCallback routine registers a power-setting callback routine to receive notifications of changes in the specified power setting.
old-location: kernel\poregisterpowersettingcallback.htm
old-project: kernel
ms.assetid: a4dd91c4-f6b1-4751-a2be-9b4872fa7bb2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PoRegisterPowerSettingCallback, kernel.poregisterpowersettingcallback, PoRegisterPowerSettingCallback routine [Kernel-Mode Driver Architecture], portn_ddaef830-5cf5-4b7f-9fa6-e29a2b9f847f.xml, PoRegisterPowerSettingCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	PoRegisterPowerSettingCallback
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# PoRegisterPowerSettingCallback function


## -description


The <b>PoRegisterPowerSettingCallback</b> routine registers a power-setting callback routine to receive notifications of changes in the specified power setting.


## -syntax


````
NTSTATUS PoRegisterPowerSettingCallback(
  _In_opt_ PDEVICE_OBJECT          DeviceObject,
  _In_     LPCGUID                 SettingGuid,
  _In_     PPOWER_SETTING_CALLBACK Callback,
  _In_opt_ PVOID                   Context,
  _Out_    PVOID                   *Handle
);
````


## -parameters




### -param DeviceObject [in, optional]

A pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that is associated with the caller of this routine. This parameter is optional. It is used internally only for debugging purposes. If this parameter is not supplied, it must be set to <b>NULL</b>.


### -param SettingGuid [in]

A pointer to the GUID that represents the power setting for this registration. When the specified power setting changes, the power manager calls the callback routine to notify the driver of the change and to supply the new value of the setting. For more information, see Remarks.


### -param Callback [in]

A pointer to a caller-implemented power-setting callback routine that the power manager calls when the specified power setting changes. For the functional prototype for the callback routine, see <a href="https://docs.microsoft.com/">Power-Setting Callback</a>.


### -param Context [in, optional]

A pointer to the context for the callback routine. This parameter is optional. It is provided so that a driver or device context can be passed to the callback routine. If this parameter is not used, it must be set to <b>NULL</b>.


### -param Handle [out]

A handle that the power manager uses to represent the callback routine. A driver must subsequently supply this handle in a call to <a href="..\ntifs\nf-ntifs-pounregisterpowersettingcallback.md">PoUnregisterPowerSettingCallback</a> to unregister the callback routine.


## -returns


<b>PoRegisterPowerSettingCallback</b> returns one of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The routine registered the callback routine.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The routine could not allocate the system resources that are required to register the callback routine.

</td>
</tr>
</table> 



## -remarks


A driver calls <b>PoRegisterPowerSettingCallback</b> to register a callback routine with the power manager. The power manager subsequently calls this callback routine to notify the driver after there is a change to the specified power setting. In addition, the power manager initializes the power setting of the driver by immediately calling the callback routine and passing the current value of the power setting. The power manager initializes the power setting of the driver this way regardless of whether the power setting has actually changed.

A driver should call <b>PoRegisterPowerSettingCallback</b> for each power setting that the driver needs to monitor. Drivers should call this routine in their <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine during initialization. Typically, most drivers pass a pointer to a device extension in the <i>Context</i> parameter.

To unregister a power-setting callback, call the <a href="..\ntifs\nf-ntifs-pounregisterpowersettingcallback.md">PoUnregisterPowerSettingCallback</a> routine.

Typically, Kernel-Mode Driver Framework (KMDF) drivers should call <b>PoRegisterPowerSettingCallback</b> from their <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a> callback function, and should call <b>PoUnregisterPowerSettingCallback</b> from their <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a> callback function. These drivers should <u>not</u> call <b>PoRegisterPowerSettingCallback</b> from their <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function; otherwise, the power-setting callback routine might be called before the driver stack is completely built.

The callback routine that is registered for a particular power setting is called when a transition in power state occurs that changes the value of the setting, or when the power manager changes the value of the setting. For example, if <i>SettingGuid</i> points to the GUID value GUID_LIDSWITCH_STATE_CHANGE, the callback routine is called when the lid to a laptop computer clicks open or closed. The <i>Value</i> parameter passed to the callback routine in this example points to a ULONG value that is 1 if the state of the lid switch changed from closed to open, and is 0 if the state of the lid switch changed from open to closed. For more information, see the power-setting GUID definitions and extensive comments in the Wdm.h header file.

The initial call to a callback routine might occur immediately, before the <b>PoRegisterPowerSettingCallback</b> call that registers the routine returns.

<b>PoRegisterPowerSettingCallback</b> can be called only at IRQL = PASSIVE_LEVEL.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>

<a href="..\ntifs\nf-ntifs-pounregisterpowersettingcallback.md">PoUnregisterPowerSettingCallback</a>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>

<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoRegisterPowerSettingCallback routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

