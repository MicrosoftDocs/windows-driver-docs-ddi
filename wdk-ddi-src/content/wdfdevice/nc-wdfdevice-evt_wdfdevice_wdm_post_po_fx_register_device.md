---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE (wdfdevice.h)
description: The EvtDeviceWdmPostPoFxRegisterDevice callback function performs device-specific operations after the framework has registered with the power framework.
old-location: wdf\evtdevicewdmpostpofxregisterdevice.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback function"]
ms.keywords: EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE, EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback, EvtDeviceWdmPostPoFxRegisterDevice, EvtDeviceWdmPostPoFxRegisterDevice callback function, kmdf.evtdevicewdmpostpofxregisterdevice, wdf.evtdevicewdmpostpofxregisterdevice, wdfdevice/EvtDeviceWdmPostPoFxRegisterDevice
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE
 - wdfdevice/EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdfdevice.h
api_name:
 - EvtDeviceWdmPostPoFxRegisterDevice
---

# EVT_WDFDEVICE_WDM_POST_PO_FX_REGISTER_DEVICE callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function performs device-specific operations after the framework has registered with the power framework.

## -parameters

### -param Device 

[in]
A handle to a framework device object.

### -param PoHandle 

[in]
A handle that represents the device’s registration with the power framework.

## -returns

An NTSTATUS value indicating success or failure of the operations performed in this callback. If failure is returned, the framework in turn  will fail <a href="/windows-hardware/drivers/kernel/irp-mn-start-device">IRP_MN_START_DEVICE</a>.

## -remarks

If you are writing a KMDF driver for a single-component device that defines multiple functional power states, you can register an <i>EvtDeviceWdmPostPoFxRegisterDevice</i> callback function to receive notification after the framework registers with the power management framework (PoFx).

To register <i>EvtDeviceWdmPostPoFxRegisterDevice</i>, a driver must call <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

The POHANDLE received in <i>EvtDeviceWdmPostPoFxRegisterDevice</i> remains valid until the driver returns from <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device">EvtDeviceWdmPrePoFxUnregisterDevice</a>.

Your driver can use the POHANDLE to call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentlatency">PoFxSetComponentLatency</a>, <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentresidency">PoFxSetComponentResidency</a>, and <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxsetcomponentwake">PoFxSetComponentWake</a> to specify latency, residency, and wake hints to the power framework.

 

Your driver can also use the POHANDLE to call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-pofxpowercontrol">PoFxPowerControl</a> to send a power control request to PoFx.

A KMDF driver for a multiple component device does not provide <i>EvtDeviceWdmPostPoFxRegisterDevice</i>. Instead, such a driver receives the POHANDLE when it calls <i>PoFxRegisterDevice</i>.  For more information, see <a href="/windows-hardware/drivers/wdf/supporting-multiple-functional-power-states-for-multiple-component-devices">Supporting Multiple Functional Power States for Multiple-Component Devices</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device">EvtDeviceWdmPrePoFxUnregisterDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>
