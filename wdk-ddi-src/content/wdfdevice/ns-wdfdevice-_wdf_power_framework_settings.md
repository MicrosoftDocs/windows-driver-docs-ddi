---
UID: NS:wdfdevice._WDF_POWER_FRAMEWORK_SETTINGS
title: "_WDF_POWER_FRAMEWORK_SETTINGS"
author: windows-driver-content
description: The WDF_POWER_FRAMEWORK_SETTINGS structure describes power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdf_power_framework_settings.htm
old-project: wdf
ms.assetid: 2512682A-4E1C-453F-8C46-E8979E46B8EF
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "_WDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS, WDF_POWER_FRAMEWORK_SETTINGS, kmdf.wdf_power_framework_settings, wdf.wdf_power_framework_settings, *PWDF_POWER_FRAMEWORK_SETTINGS, wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS, wdfdevice/PWDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS structure pointer, WDF_POWER_FRAMEWORK_SETTINGS structure"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_POWER_FRAMEWORK_SETTINGS
product: Windows
targetos: Windows
req.typenames: WDF_POWER_FRAMEWORK_SETTINGS, *PWDF_POWER_FRAMEWORK_SETTINGS
req.product: Windows 10 or later.
---

# _WDF_POWER_FRAMEWORK_SETTINGS structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure describes power management framework (PoFx) settings for single-component devices.


## -syntax


````
typedef struct _WDF_POWER_FRAMEWORK_SETTINGS {
  ULONG                                         Size;
  PFN_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE  EvtDeviceWdmPostPoFxRegisterDevice;
  PFN_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE EvtDeviceWdmPrePoFxUnregisterDevice;
  PPO_FX_COMPONENT                              Component;
  PPO_FX_COMPONENT_ACTIVE_CONDITION_CALLBACK    ComponentActiveConditionCallback;
  PPO_FX_COMPONENT_IDLE_CONDITION_CALLBACK      ComponentIdleConditionCallback;
  PPO_FX_COMPONENT_IDLE_STATE_CALLBACK          ComponentIdleStateCallback;
  PPO_FX_POWER_CONTROL_CALLBACK                 PowerControlCallback;
  PVOID                                         PoFxDeviceContext;
} WDF_POWER_FRAMEWORK_SETTINGS, *PWDF_POWER_FRAMEWORK_SETTINGS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field EvtDeviceWdmPostPoFxRegisterDevice

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a> event callback function, or NULL.


### -field EvtDeviceWdmPrePoFxUnregisterDevice

A pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a> event callback function, or NULL.


### -field Component

A pointer to a <a href="..\wudfwdm\ns-wudfwdm-_po_fx_component_v2.md">PO_FX_COMPONENT</a> structure that describes the only component
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



The <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure is used an input to <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

To initialize its <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure, your driver should call <a href="..\wdfdevice\nf-wdfdevice-wdf_power_framework_settings_init.md">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>.

For more information, see <a href="https://msdn.microsoft.com/F96214C9-702D-402E-B873-5DF57C521B34">Supporting Functional Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406637">Overview of the Power Management Framework</a>.

This structure is not applicable to KMDF client drivers for multiple-component devices.
 




## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>



<a href="..\wdfdevice\nf-wdfdevice-wdf_power_framework_settings_init.md">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_FRAMEWORK_SETTINGS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

