---
UID: NC:wdm.GET_IDLE_WAKE_INFO
title: GET_IDLE_WAKE_INFO
author: windows-driver-content
description: The GetIdleWakeInfo routine enables the driver for a device to discover the device power states from which the device can signal a wake event.
old-location: kernel\getidlewakeinfo.htm
old-project: kernel
ms.assetid: 51DE471E-5409-4ED9-BC50-29D18E8F5A16
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.getidlewakeinfo, GetIdleWakeInfo routine [Kernel-Mode Driver Architecture], GetIdleWakeInfo, GET_IDLE_WAKE_INFO, GET_IDLE_WAKE_INFO, wdm/GetIdleWakeInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	GetIdleWakeInfo
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_IDLE_WAKE_INFO callback


## -description


The <i>GetIdleWakeInfo</i> routine enables the driver for a device to discover the device power states from which the device can signal a wake event.


## -prototype


````
GET_IDLE_WAKE_INFO GetIdleWakeInfo;

NTSTATUS GetIdleWakeInfo(
  _In_opt_ PVOID              Context,
  _In_     SYSTEM_POWER_STATE SystemPowerState,
  _Out_    PDEVICE_WAKE_DEPTH DeepestWakeableDstate
)
{ ... }
````


## -parameters




### -param Context [in, optional]

A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="..\wdm\ns-wdm-_d3cold_support_interface.md">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.


### -param SystemPowerState [in]

System power state. Set this parameter to one of the following <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> enumeration values:
<ul>
<li><b>PowerSystemWorking</b></li>
<li><b>PowerSystemSleeping1</b></li>
<li><b>PowerSystemSleeping2</b></li>
<li><b>PowerSystemSleeping3</b></li>
<li><b>PowerSystemHibernate</b></li>
</ul>These values represent system power states S0 (system working state) through S4. For the <i>SystemPowerState</i> value supplied by the caller, the routine determines the deepest device power state from which the device can issue a wake signal.


### -param DeepestWakeableDstate [out]

Deepest wakeable Dx state. This parameter is a pointer to a <a href="..\wdm\ne-wdm-_device_wake_depth.md">DEVICE_WAKE_DEPTH</a> variable. If the call is successful, the routine writes one of the following enumeration values to this variable:
<ul>
<li><b>DeviceWakeDepthNotWakeable</b></li>
<li><b>DeviceWakeDepthD0</b></li>
<li><b>DeviceWakeDepthD1</b></li>
<li><b>DeviceWakeDepthD2</b></li>
<li><b>DeviceWakeDepthD3hot</b></li>
<li><b>DeviceWakeDepthD3cold</b></li>
</ul>A value in the range <b>DeviceWakeDepthD0</b> to <b>DeviceWakeDepthD3cold</b> indicates the lowest-powered Dx state from which the device can send a wake signal when the computer is in the system power state specified by the <i>SystemPowerState</i> parameter. <b>DeviceWakeDepthNotWakeable</b> indicates that there is no device power state from which the device can send a wake signal when the computer is in the system power state specified by <i>SystemPowerState</i>.

If the routine cannot determine the deepest wakeable device state (perhaps because the platform firmware does not contain this information), the call fails and the routine returns an error status code. If a <i>GetIdleWakeInfo</i> call fails for any <i>SystemPowerState</i> parameter value in the range <b>PowerSystemWorking</b> to <b>PowerSystemHibernate</b>, it will fail for all such values.


## -returns


The <i>GetIdleWakeInfo</i> routine returns STATUS_SUCCESS if it successfully retrieves the deepest wakeable device state. Otherwise, it returns an appropriate error status code.



## -remarks


For the system power state specified by the caller, this routine tries to determine the lowest-powered device power state from which the device can signal a wake event to the processor. If successful, the routine writes the device power state to the location pointed to by the <i>DeepestWakeableDstate</i> parameter, and returns STATUS_SUCCESS. Or, if the routine determines that the device cannot signal a wake event from any device power state, the routine writes the value <b>DeviceWakeDepthNotWakeable</b> to this location, and returns STATUS_SUCCESS.

The driver for a device uses the information supplied by the <i>GetIdleWakeInfo</i> routine to determine the conditions under which the device can signal a wake event. A device that needs to be able to signal certain wake events should not enter a device power state from which it cannot signal these events. For some types of devices, the wake signals that the device should send when the computer is in the S0 (working) system power state differ from those that the device should send when the computer appears to be off.

For example, when a card is inserted into a PCI Express card slot, and the PCI Express hot-plug controller device for the slot is in the D0 device power state, this device signals an interrupt to the processor. However, if the controller device is in a low-power Dx state when the card is inserted, the system power state of the computer might determine whether this device should signal a wake event to the processor. Ideally, the controller device should behave as follows:
<ul>
<li>If the computer is in the S0 (working) system power state, the device should signal a wake event to the processor.</li>
<li>If the computer is sleeping (in a low-power Sx state), the device should not signal a wake event.</li>
</ul>Some older devices might not support this ideal behavior. If the PCI Express hot-plug controller device in this example can signal a wake event only when the computer is in the S3 state, the driver (which, in this case, is the inbox Pci.sys driver) for the controller should keep the controller in D0 when the computer is in S0 (and is not preparing to enter a sleeping state).

The driver in this example can call the <i>GetIdleWakeInfo</i> routine to determine whether the hot-plug controller device should leave the D0 state while the computer is in S0. For this call, the driver sets <i>SystemPowerState</i> = <b>PowerSystemWorking</b>. This device should not leave the D0 state (when the computer is in S0) in either of the following cases:
<ul>
<li>The <i>GetIdleWakeInfo</i> call sets the output parameter to either <b>DeviceWakeDepthNotWakeable</b> or <b>DeviceWakeDepthD0</b> and returns STATUS_SUCCESS.</li>
<li>The <i>GetIdleWakeInfo</i> call fails and returns an error status code.</li>
</ul>The driver should interpret either of these results to mean that the device cannot signal a wake event when the computer is in S0. Based on this information, the driver should keep the device in D0 until the computer prepares to exit S0.

The drivers for most devices can treat an output value of <b>DeviceWakeDepthD0</b> the same as <b>DeviceWakeDepthNotWakeable</b>. Only a few drivers might have a reason to arm a wake signal when their devices are in D0. These are drivers for simple devices that monitor external events that trigger wake signals regardless of the whether the devices are in D0 or low-power Dx states. An example of such a device is a power button or a sleep button on a computer.

The <i>GetIdleWakeInfo</i> routine queries the underlying bus driver and ACPI system firmware to determine the lowest device power state from which the device can signal a wake event. If the bus driver and firmware cannot supply this information, the routine fails and returns an error status code.


The <a href="..\wdm\ns-wdm-_device_capabilities.md">DEVICE_CAPABILITIES</a> structure includes a <b>DeviceWake</b> member that provides information similar to that available from the <i>GetIdleWakeInfo</i> routine. However, the information in the <b>DeviceWake</b> member applies only to the system low-power states S1 to S4. For some devices, the information in the <b>DeviceWake</b> member might also apply to the S0 system power state, but drivers should not rely on such behavior. Only the <i>GetIdleWakeInfo</i> routine reliably reports the ability of a device to signal a wake event if the computer is in S0.

An inline helper function, <b>MapWakeDepthToDstate</b>, is provided to convert the <a href="..\wdm\ne-wdm-_device_wake_depth.md">DEVICE_WAKE_DEPTH</a> output value from the <i>GetIdleWakeInfo</i> routine to a <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a> value that can be used as an input parameter by the <a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a> routine.



## -see-also

<a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>

<a href="..\wdm\ne-wdm-_device_wake_depth.md">DEVICE_WAKE_DEPTH</a>

<a href="..\wdm\nf-wdm-porequestpowerirp.md">PoRequestPowerIrp</a>

<a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>

<a href="..\wdm\ns-wdm-_device_capabilities.md">DEVICE_CAPABILITIES</a>

<a href="..\wdm\ns-wdm-_d3cold_support_interface.md">D3COLD_SUPPORT_INTERFACE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20GET_IDLE_WAKE_INFO routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

