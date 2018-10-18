---
UID: NF:wdfdevice.WdfDeviceWdmAssignPowerFrameworkSettings
title: WdfDeviceWdmAssignPowerFrameworkSettings function
author: windows-driver-content
description: The WdfDeviceWdmAssignPowerFrameworkSettings method registers power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdfdevicewdmassignpowerframeworksettings.htm
tech.root: wdf
ms.assetid: 676A458E-A6E0-4F09-AAF2-21EA122EF74D
ms.date: 2/26/2018
ms.keywords: WdfDeviceWdmAssignPowerFrameworkSettings, WdfDeviceWdmAssignPowerFrameworkSettings method, kmdf.wdfdevicewdmassignpowerframeworksettings, wdf.wdfdevicewdmassignpowerframeworksettings, wdfdevice/WdfDeviceWdmAssignPowerFrameworkSettings
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceWdmAssignPowerFrameworkSettings
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceWdmAssignPowerFrameworkSettings function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method registers  power management framework (PoFx) settings for single-component devices.


## -parameters




### -param Device [in]

A handle to the framework device object for which PoFx settings are being specified.


### -param PowerFrameworkSettings [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a> structure that describes the client driver’s PoFx settings.


## -returns



The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method returns an NTSTATUS value that indicates success or failure of the operation.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure is incorrect. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's power policy owner.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid <i>Settings</i> value is detected.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method applies only to single-component devices.

After calling this method, the client driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545903">WdfDeviceAssignS0IdleSettings</a> and set the <b>IdleTimeoutType</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b>.

A driver must call <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> before or during the first time a device starts. Because a device can start more than once, for example if resource rebalancing occurs, a driver might call this method from within <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>  or  <a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>. The framework calls these functions only once, even if the device is started more than once.

Alternatively, the driver could keep track of whether it has already called <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>, and call it from one of the following callback functions: <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>, <a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a>, <a href="https://msdn.microsoft.com/38d74ce1-9d9d-4da5-a2b3-579048850b28">EvtDeviceD0EntryPostInterruptsEnabled</a>, or <a href="https://msdn.microsoft.com/13d7fbc6-6f93-4ef9-abd4-f2adc4e8e23a">EvtDeviceSelfManagedIoRestart</a>.

If your driver calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> more than once, the framework generates a verifier error.

The power management framework (PoFx) is available only on Windows 8 and later. When running on an operating system that does not support PoFx, <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> takes no action and returns STATUS_SUCCESS.

For more information, see <a href="https://msdn.microsoft.com/F96214C9-702D-402E-B873-5DF57C521B34">Supporting Functional Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406637">Overview of the Power Management Framework</a>.


#### Examples

In the following code example, the driver initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a> structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406492">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>  function. The driver then manually sets some of the members of the structure, and then calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
WDF_POWER_FRAMEWORK_SETTINGS poFxSettings;

WDF_POWER_FRAMEWORK_SETTINGS_INIT(&amp;poFxSettings);

poFxSettings.EvtDeviceWdmPostPoFxRegisterDevice = 
                        SingleCompWdmEvtDeviceWdmPostPoFxRegisterDevice;
poFxSettings.EvtDeviceWdmPrePoFxUnregisterDevice =
                        SingleCompWdmEvtDeviceWdmPrePoFxUnregisterDevice;

poFxSettings.Component = &amp;component;
poFxSettings.ComponentIdleStateCallback = 
                        SingleCompWdmIdleStateCallback;
poFxSettings.PoFxDeviceContext = (PVOID) Device;
    
status = WdfDeviceWdmAssignPowerFrameworkSettings(Device, &amp;poFxSettings);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/D663C47D-C59E-4210-84D8-9773A3003990">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406492">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>
 

 

