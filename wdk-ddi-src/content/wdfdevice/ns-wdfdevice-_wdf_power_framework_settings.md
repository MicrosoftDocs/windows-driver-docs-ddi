---
UID: NS:wdfdevice._WDF_POWER_FRAMEWORK_SETTINGS
title: "_WDF_POWER_FRAMEWORK_SETTINGS"
author: windows-driver-content
description: The WDF_POWER_FRAMEWORK_SETTINGS structure describes power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdf_power_framework_settings.htm
tech.root: wdf
ms.assetid: 2512682A-4E1C-453F-8C46-E8979E46B8EF
ms.date: 02/26/2018
ms.keywords: "*PWDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS structure pointer, WDF_POWER_FRAMEWORK_SETTINGS, WDF_POWER_FRAMEWORK_SETTINGS structure, _WDF_POWER_FRAMEWORK_SETTINGS, kmdf.wdf_power_framework_settings, wdf.wdf_power_framework_settings, wdfdevice/PWDF_POWER_FRAMEWORK_SETTINGS, wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS"
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_POWER_FRAMEWORK_SETTINGS
product:
- Windows
targetos: Windows
req.typenames: WDF_POWER_FRAMEWORK_SETTINGS, *PWDF_POWER_FRAMEWORK_SETTINGS
---

# _WDF_POWER_FRAMEWORK_SETTINGS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure describes power management framework (PoFx) settings for single-component devices.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceWdmPostPoFxRegisterDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a> event callback function, or NULL.


### -field EvtDeviceWdmPrePoFxUnregisterDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/D663C47D-C59E-4210-84D8-9773A3003990">EvtDeviceWdmPrePoFxUnregisterDevice</a> event callback function, or NULL.


### -field Component

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439575">PO_FX_COMPONENT</a> structure that describes the only component
     in the single-component device, or NULL. If NULL, KMDF defaults to F0 support only for this component. This structure specifies the number and attributes of the F-states that the component supports, as well as the deepest Fx state from which the component can awaken.


### -field ComponentActiveConditionCallback

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a> callback routine, or NULL. The power management framework (PoFx) calls this callback function when a component becomes active. While in the Active condition, the component is guaranteed to be in F0.


### -field ComponentIdleConditionCallback

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a> callback function, or NULL. PoFx calls this callback function when a component becomes idle. While in the Idle condition, the component may be in any F-state, including F0.


### -field ComponentIdleStateCallback

A pointer to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a> callback function, or NULL. PoFx calls this callback function when the F-state of the component changes.


### -field PowerControlCallback

A pointer to the client driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a> callback function, or NULL. PoFx calls this routine to pass a request for a power control operation directly to the driver. If your driver does not support any power control codes, set this parameter to NULL.


### -field PoFxDeviceContext

A context pointer that the framework supplies to  <a href="https://msdn.microsoft.com/library/windows/hardware/hh406416">ComponentActiveConditionCallback</a>, 
    <a href="https://msdn.microsoft.com/library/windows/hardware/hh406420">ComponentIdleConditionCallback</a>,  <a href="https://msdn.microsoft.com/library/windows/hardware/hh450931">ComponentIdleStateCallback</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439564">PowerControlCallback</a>.


## -remarks



The <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure is used an input to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

To initialize its <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/hh406492">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>.

For more information, see <a href="https://msdn.microsoft.com/F96214C9-702D-402E-B873-5DF57C521B34">Supporting Functional Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406637">Overview of the Power Management Framework</a>.

This structure is not applicable to KMDF client drivers for multiple-component devices.
 




## -see-also




<a href="https://msdn.microsoft.com/4CE227F5-9ED4-4484-AFBF-44D1260EB99D">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://msdn.microsoft.com/D663C47D-C59E-4210-84D8-9773A3003990">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406492">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>
 

 

