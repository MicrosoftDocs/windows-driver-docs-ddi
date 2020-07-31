---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE (wdfdevice.h)
description: The EvtDeviceWdmPrePoFxUnregisterDevice callback function performs device-specific operations before the framework deletes a specified registration with the power framework.
old-location: wdf\evtdevicewdmprepofxunregisterdevice.htm
tech.root: wdf
ms.assetid: D663C47D-C59E-4210-84D8-9773A3003990
ms.date: 02/26/2018
keywords: ["EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback function"]
ms.keywords: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE, EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback, EvtDeviceWdmPrePoFxUnregisterDevice, EvtDeviceWdmPrePoFxUnregisterDevice callback function, kmdf.evtdevicewdmprepofxunregisterdevice, wdf.evtdevicewdmprepofxunregisterdevice, wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice
f1_keywords:
 - "wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice"
 - "EvtDeviceWdmPrePoFxUnregisterDevice"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdfdevice.h
api_name:
- EvtDeviceWdmPrePoFxUnregisterDevice
targetos: Windows
req.typenames: 
---

# EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function performs device-specific operations before the framework deletes a specified registration with the power framework.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PoHandle [in]

A handle that represents the device’s registration with the power framework.


## -remarks



The <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function applies only to single-component devices.

To register an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

A driver can provide this callback function if it must perform any additional operations before the framework unregisters the specified POHANDLE.

 After the driver has returned from this callback, it is no longer safe to use this POHANDLE.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device">EvtDeviceWdmPostPoFxRegisterDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings">WdfDeviceWdmAssignPowerFrameworkSettings</a>
 

 

