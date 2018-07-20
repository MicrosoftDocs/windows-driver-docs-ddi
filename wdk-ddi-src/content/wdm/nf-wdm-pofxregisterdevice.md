---
UID: NF:wdm.PoFxRegisterDevice
title: PoFxRegisterDevice function
author: windows-driver-content
description: The PoFxRegisterDevice routine registers a device with the power management framework (PoFx).
old-location: kernel\pofxregisterdevice.htm
tech.root: kernel
ms.assetid: 41A8B278-3735-41CB-B8D1-45FBF04465AD
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: PoFxRegisterDevice, PoFxRegisterDevice routine [Kernel-Mode Driver Architecture], kernel.pofxregisterdevice, wdm/PoFxRegisterDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
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
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
api_name:
-	PoFxRegisterDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# PoFxRegisterDevice function


## -description


The <b>PoFxRegisterDevice</b> routine registers a device with the power management framework (PoFx).


## -parameters




### -param Pdo [in]

A pointer to a <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">physical device object</a> (PDO). This parameter points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the physical device that is being registered. The caller is the power policy owner for the device, which is typically the device's function driver.


### -param Device [in]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a> structure that contains the registration information for the device. This structure contains pointers to a set of callback routines that are implemented by the device driver. PoFx calls these routines to communicate with the driver.


### -param Handle [out]

A pointer to a location into which the routine writes a handle that represents the registration of the device with PoFx. The device driver passes this handle as an input parameter to the other <b>PoFx<i>Xxx</i></b> routines that it calls. The driver must first call <b>PoFxRegisterDevice</b> to register the device before the driver calls any other <b>PoFx<i>Xxx</i></b> routines to power-manage the device.


## -returns



<b>PoFxRegisterDevice</b> returns <b>STATUS_SUCCESS</b> if the routine successfully registers the device. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_INVALID_PARAMETER</b></b></dt>
</dl>
</td>
<td width="60%">
<i>Pdo</i> is NULL; or the <b>PPO_FX_DEVICE</b> structure has an invalid version number or a component count of zero; or the number of idle states specified for a component is zero; or the description of an idle state is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_DEVICE_NOT_READY</b></b></dt>
</dl>
</td>
<td width="60%">
The device is not ready.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>STATUS_INSUFFICIENT_RESOURCES</b></b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to complete the registration.

</td>
</tr>
</table>
 




## -remarks



A device driver typically calls this routine from the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request handler. The driver must not call this routine before the device receives an <b>IRP_MN_START_DEVICE</b> request. The device receives the first <b>IRP_MN_START_DEVICE</b> request when the device is being started for the first time. The device receives an additional <b>IRP_MN_START_DEVICE</b> request each time the device is restarted after being stopped for resource balancing. A <b>PoFxRegisterDevice</b> call to register a device that is already registered is a fatal error and causes a bug check. Note that PoFx performs a deep-copy of the device structures into its memory. 

Before the driver calls <b>PoFxRegisterDevice</b>, the device must meet the following conditions:

<ul>
<li>The device (that is, the PDO) is not already registered with PoFx.</li>
<li>The device is in the D0 (fully on) power state.</li>
<li>The device is in the running condition.</li>
<li>Every component in the device is in the F0 (fully on) power state.</li>
<li>Every component is in the active condition.</li>
</ul>
By registering the device with PoFx, the driver assumes the responsibility for informing PoFx when a component is actively being used and when the component is idle. While the device is registered, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406650">PoFxActivateComponent</a> routine to gain access to a component's hardware registers, and the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406717">PoFxIdleComponent</a> routine to notify PoFx when the driver no longer requires access to the component.

After a driver calls <b>PoFxRegisterDevice</b> to register a device with PoFx, all components in the device are fully on and in the active condition so that the driver can finish initializing the hardware. To start active power management, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439551">PoFxStartDevicePowerManagement</a> routine.

By default, <b>PoFxStartDevicePowerManagement</b> switches all components to the idle condition. If the driver requires a component to be in the active condition immediately after power management starts, the driver must explicitly activate the component by calling the <b>PoFxActivateComponent</b> routine, and this call must occur after the <b>PoFxRegisterDevice</b> call but before the <b>PoFxStartDevicePowerManagement</b> call.

Typically, the Kernel-Mode Driver Framework (KMDF) driver for a single-component device does not call <b>PoFxRegisterDevice</b> to register the device with PoFx. Instead, this driver receives a PoFx registration handle when KMDF calls the driver's <a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a> callback function. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-multiple-functional-power-states-for-single-component-devices">Supporting Multiple Functional Power States for Single-Component Devices</a>.

For information about how the KMDF driver for a multiple-component device registers with PoFx, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-multiple-functional-power-states-for-multiple-component-devices">Supporting Multiple Functional Power States for Multiple-Component Devices</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439585">PO_FX_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406650">PoFxActivateComponent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406717">PoFxIdleComponent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439551">PoFxStartDevicePowerManagement</a>
 

 

