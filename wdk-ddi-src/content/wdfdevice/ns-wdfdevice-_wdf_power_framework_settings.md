---
UID: NS:wdfdevice._WDF_POWER_FRAMEWORK_SETTINGS
title: _WDF_POWER_FRAMEWORK_SETTINGS (wdfdevice.h)
description: The WDF_POWER_FRAMEWORK_SETTINGS structure describes power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdf_power_framework_settings.htm
tech.root: wdf
ms.assetid: 2512682A-4E1C-453F-8C46-E8979E46B8EF
ms.date: 02/26/2018
keywords: ["WDF_POWER_FRAMEWORK_SETTINGS structure"]
ms.keywords: "*PWDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS, PWDF_POWER_FRAMEWORK_SETTINGS structure pointer, WDF_POWER_FRAMEWORK_SETTINGS, WDF_POWER_FRAMEWORK_SETTINGS structure, _WDF_POWER_FRAMEWORK_SETTINGS, kmdf.wdf_power_framework_settings, wdf.wdf_power_framework_settings, wdfdevice/PWDF_POWER_FRAMEWORK_SETTINGS, wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.33
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
targetos: Windows
req.typenames: WDF_POWER_FRAMEWORK_SETTINGS, *PWDF_POWER_FRAMEWORK_SETTINGS
f1_keywords:
 - _WDF_POWER_FRAMEWORK_SETTINGS
 - wdfdevice/_WDF_POWER_FRAMEWORK_SETTINGS
 - PWDF_POWER_FRAMEWORK_SETTINGS
 - wdfdevice/PWDF_POWER_FRAMEWORK_SETTINGS
 - WDF_POWER_FRAMEWORK_SETTINGS
 - wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_POWER_FRAMEWORK_SETTINGS
---

# _WDF_POWER_FRAMEWORK_SETTINGS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure describes power management framework (PoFx) settings for single-component devices.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field EvtDeviceWdmPostPoFxRegisterDevice

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device">EvtDeviceWdmPostPoFxRegisterDevice</a> event callback function, or NULL.

### -field EvtDeviceWdmPrePoFxUnregisterDevice

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device">EvtDeviceWdmPrePoFxUnregisterDevice</a> event callback function, or NULL.

### -field Component

A pointer to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_po_fx_component_v1">PO_FX_COMPONENT</a> structure that describes the only component
     in the single-component device, or NULL. If NULL, KMDF defaults to F0 support only for this component. This structure specifies the number and attributes of the F-states that the component supports, as well as the deepest Fx state from which the component can awaken.

### -field ComponentActiveConditionCallback

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a> callback routine, or NULL. The power management framework (PoFx) calls this callback function when a component becomes active. While in the Active condition, the component is guaranteed to be in F0.

### -field ComponentIdleConditionCallback

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a> callback function, or NULL. PoFx calls this callback function when a component becomes idle. While in the Idle condition, the component may be in any F-state, including F0.

### -field ComponentIdleStateCallback

A pointer to the driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a> callback function, or NULL. PoFx calls this callback function when the F-state of the component changes.

### -field PowerControlCallback

A pointer to the client driver's <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a> callback function, or NULL. PoFx calls this routine to pass a request for a power control operation directly to the driver. If your driver does not support any power control codes, set this parameter to NULL.

### -field PoFxDeviceContext

A context pointer that the framework supplies to  <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_active_condition_callback">ComponentActiveConditionCallback</a>, 
    <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_condition_callback">ComponentIdleConditionCallback</a>,  <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_component_idle_state_callback">ComponentIdleStateCallback</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-po_fx_power_control_callback">PowerControlCallback</a>.

### -field PoFxDeviceFlags

A value of type ULONGLONG containing the bitwise **OR** of the following values related to the [Directed Power Management Framework](/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework). This field is available starting in KMDF version 1.33 and UMDF 2.33.

**PO_FX_DEVICE_FLAG_DFX_CHILDREN_OPTIONAL**

When the Directed Power Framework ("DFx") is enabled on a device, typically child devices also enable DFx. However, in some cases (for example a pure software device), a child device does not implement power management. Set this flag to allow such a child device to skip DFx.

To set this flag on behalf of child devices, the parent WDF driver must:

* [Opt into DFx](/windows-hardware/drivers/kernel/introduction-to-the-directed-power-management-framework#requirements-for-wdf-non-miniport-drivers)
* Not be a bus driver
* Have at least one virtual child device created through a side-band channel (for example an upper filter or device created by calling [**SwDeviceCreate**](/windows/win32/api/swdevice/nf-swdevice-swdevicecreate)

For drivers targeting pre-v33 WDF, instead specify the INF directive: **WdfDirectedPowerTransitionChildrenOptional**, which is available starting in Windows 10, version 1903. If the driver specifies the INF directive and sets this flag, the INF directive takes precedence.

**PO_FX_DEVICE_FLAG_DISABLE_FAST_RESUME**

This is required to implement **IRP_MN_QUERY_DEVICE_RELATIONS**/PowerRelations between two devices. 

By default, WDF implements fast resume, which means that during system wakeup, the power policy owner in a device stack completes an S0-IRP without waiting to request and complete a D0-IRP. This does not work well with PowerRelations. 

To make PowerRelations works properly, if a device depends on another device to enter D0 first, the second device should set this flag to opt out of fast resume.

In some cases, global policy may disable fast resume globally even if this flag is not set.

### -field DirectedPoFxEnabled

A WDF_TRI_STATE-typed enumerator that indicates whether the device enables Directed Power Management Framework (DFx). Available starting in KMDF version 1.33 and UMDF 2.33.

**WdfTrue** - DFx is enabled.
**WdfFalse** – DFx is disabled.
**WdfUseDefault** - The default value if the driver does not set one. This value has the same meaning as **WdfTrue**.

Directed PoFx (DFx) was implemented starting in Windows 10, version 1903 as an option for drivers that use **SystemManagedIdleTimeout** or **SystemManagedIdleTimeoutWithHint**.

 - For a driver targeting pre-v31 WDF, set the INF directive **WdfDirectedPowerTransitionEnable** to 1 to opt in to DFx.
 - For a driver targeting v31+ WDF, DFx is enabled by default. The driver can set **WdfDirectedPowerTransitionEnable** to zero to opt out of DFx.
 - For a driver targeting v33+ WDF, DFx is also enabled by default. The driver can either set **WdfDirectedPowerTransitionEnable** to zero or set this field to **WdfFalse** (recommended) to opt out of DFx. If both are set, the INF directive takes precedence.


## -remarks

The <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure is used an input to <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

To initialize its <b>WDF_POWER_FRAMEWORK_SETTINGS</b> structure, your driver should call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_power_framework_settings_init">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>.

For UMDF, only **Size**, **PoFxDeviceFlags**, and **DirectedPoFxEnabled** are used. Other fields are ignored and must be set to zero. The framework does this automatically when a UMDF driver calls <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_power_framework_settings_init">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>.

For more information, see <a href="/windows-hardware/drivers/wdf/supporting-functional-power-states">Supporting Functional Power States</a> and <a href="/windows-hardware/drivers/kernel/overview-of-the-power-management-framework">Overview of the Power Management Framework</a>.

This structure is not applicable to KMDF client drivers for multiple-component devices.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_power_framework_settings_init">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>