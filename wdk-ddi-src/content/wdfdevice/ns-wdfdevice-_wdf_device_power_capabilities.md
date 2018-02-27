---
UID: NS:wdfdevice._WDF_DEVICE_POWER_CAPABILITIES
title: "_WDF_DEVICE_POWER_CAPABILITIES"
author: windows-driver-content
description: The WDF_DEVICE_POWER_CAPABILITIES structure describes a device's power capabilities.
old-location: wdf\wdf_device_power_capabilities.htm
old-project: wdf
ms.assetid: 56bb271f-d69c-4523-87cb-4922b405f808
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PWDF_DEVICE_POWER_CAPABILITIES, DFDeviceObjectGeneralRef_6678d7f5-5de1-473f-a2db-777405225add.xml, PWDF_DEVICE_POWER_CAPABILITIES, PWDF_DEVICE_POWER_CAPABILITIES structure pointer, WDF_DEVICE_POWER_CAPABILITIES, WDF_DEVICE_POWER_CAPABILITIES structure, _WDF_DEVICE_POWER_CAPABILITIES, kmdf.wdf_device_power_capabilities, wdf.wdf_device_power_capabilities, wdfdevice/PWDF_DEVICE_POWER_CAPABILITIES, wdfdevice/WDF_DEVICE_POWER_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_DEVICE_POWER_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_POWER_CAPABILITIES, *PWDF_DEVICE_POWER_CAPABILITIES
req.product: Windows 10 or later.
---

# _WDF_DEVICE_POWER_CAPABILITIES structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_DEVICE_POWER_CAPABILITIES structure describes a device's power capabilities.


## -syntax


````
typedef struct _WDF_DEVICE_POWER_CAPABILITIES {
  ULONG              Size;
  WDF_TRI_STATE      DeviceD1;
  WDF_TRI_STATE      DeviceD2;
  WDF_TRI_STATE      WakeFromD0;
  WDF_TRI_STATE      WakeFromD1;
  WDF_TRI_STATE      WakeFromD2;
  WDF_TRI_STATE      WakeFromD3;
  DEVICE_POWER_STATE DeviceState[PowerSystemMaximum];
  DEVICE_POWER_STATE DeviceWake;
  SYSTEM_POWER_STATE SystemWake;
  ULONG              D1Latency;
  ULONG              D2Latency;
  ULONG              D3Latency;
  DEVICE_POWER_STATE IdealDxStateForSx;
} WDF_DEVICE_POWER_CAPABILITIES, *PWDF_DEVICE_POWER_CAPABILITIES;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field DeviceD1

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device supports device sleeping state D1. For more information about the <b>WDF_TRI_STATE</b> value, see the following Remarks section.


### -field DeviceD2

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device supports device sleeping state D2. 


### -field WakeFromD0

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device can respond to a wake signal while in its D0 state. 


### -field WakeFromD1

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device can respond to a wake signal while in its D1 state. 


### -field WakeFromD2

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device can respond to a wake signal while in its D2 state. 


### -field WakeFromD3

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed value that indicates, if set to <b>WdfTrue</b>, that the device can respond to a wake signal while in its D3 state. 


### -field DeviceState

An array of DEVICE_POWER_STATE-typed values that indicates the most-powered device state that the device supports for each system power state. This array uses the SYSTEM_POWER_STATE enumeration as index values. If an array element's value is <b>PowerDeviceMaximum</b>, the framework uses whatever value that the operating system has stored for that element. The DEVICE_POWER_STATE and SYSTEM_POWER_STATE enumerations are defined in <i>wdm.h</i>. For more information about the <b>DeviceState</b> member, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543087">DeviceState</a>.


### -field DeviceWake

A DEVICE_POWER_STATE-typed value that indicates the lowest device power state from which the device can send a wake signal to the system. If this value is <b>PowerDeviceMaximum</b>, the framework uses whatever value is currently stored in the system for this member. 


### -field SystemWake

A SYSTEM_POWER_STATE-typed value that indicates the lowest system power state from which the device can send a wake signal to the system. If this value is <b>PowerSystemMaximum</b>, the framework uses whatever value is currently stored in the system for this member. SYSTEM_POWER_STATE values are defined in <i>wdm.h</i>.


### -field D1Latency

The approximate time, in 100-nanosecond units, that the device requires to return to its D0 state from its D1 state. If this value is -1, the framework uses whatever value is currently stored in the system for this member. 


### -field D2Latency

The approximate time, in 100-nanosecond units, that the device requires to return to its D0 state from its D2 state. If this value is -1, the framework uses whatever value is currently stored in the system for this member. 


### -field D3Latency

The approximate time, in 100-nanosecond units, that the device requires to return to its D0 state from its D3 state. If this value is -1, the framework uses whatever value is currently stored in the system for this member. 


### -field IdealDxStateForSx

A DEVICE_POWER_STATE-typed value that indicates the <a href="https://msdn.microsoft.com/f594a63f-10ce-439d-abe3-d342555d98f0">device sleeping state</a> that the device should enter when the system enters any <a href="https://msdn.microsoft.com/2fd883b5-4e89-4ce9-b75a-b821348ac860">system sleeping state</a> and the device is not enabled to wake the system. If this value is zero, the framework uses <b>PowerDeviceD3</b>. This value cannot be <b>PowerDeviceD0</b>.

If a driver specifies an <b>IdealDxStateForSx</b> value that represents a higher-powered device sleeping state than the device's stack has specified in the device's <a href="https://msdn.microsoft.com/library/windows/hardware/ff543087">DeviceState</a> array, the framework uses the lower-powered state that is in the array. For example, if the driver specifies an <b>IdealDxStateForSx</b> value of D1 and the device's <b>DeviceState</b> array specifies D2, the framework uses D2. 


## -remarks



The WDF_DEVICE_POWER_CAPABILITIES structure is used as input to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetpowercapabilities.md">WdfDeviceSetPowerCapabilities</a>.

Several members use the <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a> type. For these members, the following rules apply:

<ul>
<li>
A value of <b>WdfTrue</b> indicates that the device supports the capability and a value of <b>WdfFalse</b> indicates it does not. 

</li>
<li>
Function drivers and filter drivers can specify <b>WdfTrue</b> or <b>WdfFalse</b>, or a value of <b>WdfUseDefault</b> to indicate that the framework should use the value that was provided by a lower driver in the stack. For example, if a bus driver specifies <b>WdfTrue</b> for <b>DeviceD1</b> and the device's function driver specifies <b>WdfUseDefault</b>, the framework uses <b>WdfTrue</b> for the capability.

</li>
<li>
When a bus driver calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetpowercapabilities.md">WdfDeviceSetPowerCapabilities</a> after it <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-device-objects-in-a-bus-driver">creates a device object</a> for a child device, it should specify <b>WdfTrue</b> or <b>WdfFalse</b>. A bus driver can specify <b>WdfUseDefault</b> for a child device, but in this case <b>WdfUseDefault</b> is the same as <b>WdfFalse</b>.

</li>
</ul>
To initialize a WDF_DEVICE_POWER_CAPABILITIES structure, a driver should call <a href="..\wdfdevice\nf-wdfdevice-wdf_device_power_capabilities_init.md">WDF_DEVICE_POWER_CAPABILITIES_INIT</a>.




## -see-also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_capabilities.md">WDF_DEVICE_PNP_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_POWER_CAPABILITIES structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

