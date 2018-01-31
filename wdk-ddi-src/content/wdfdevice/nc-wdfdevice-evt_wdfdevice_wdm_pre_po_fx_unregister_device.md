---
UID: NC:wdfdevice.EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
title: EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE
author: windows-driver-content
description: The EvtDeviceWdmPrePoFxUnregisterDevice callback function performs device-specific operations before the framework deletes a specified registration with the power framework.
old-location: wdf\evtdevicewdmprepofxunregisterdevice.htm
old-project: wdf
ms.assetid: D663C47D-C59E-4210-84D8-9773A3003990
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdevicewdmprepofxunregisterdevice, EvtDeviceWdmPrePoFxUnregisterDevice callback function, EvtDeviceWdmPrePoFxUnregisterDevice, EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE, EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE, wdfdevice/EvtDeviceWdmPrePoFxUnregisterDevice, kmdf.evtdevicewdmprepofxunregisterdevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceWdmPrePoFxUnregisterDevice
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function performs device-specific operations before the framework deletes a specified registration with the power framework.


## -prototype


````
EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE EvtDeviceWdmPrePoFxUnregisterDevice;

void EvtDeviceWdmPrePoFxUnregisterDevice(
  _In_ WDFDEVICE Device,
  _In_ POHANDLE  PoHandle
)
{ ... }
````


## -parameters




#### - Device [in]

A handle to a framework device object.


#### - PoHandle [in]

A handle that represents the device’s registration with the power framework.


## -returns


This callback function does not return a value.



## -remarks


The <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function applies only to single-component devices.

To register an <i>EvtDeviceWdmPrePoFxUnregisterDevice</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

A driver can provide this callback function if it must perform any additional operations before the framework unregisters the specified POHANDLE.

 After the driver has returned from this callback, it is no longer safe to use this POHANDLE.



## -see-also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md">WdfDeviceWdmAssignPowerFrameworkSettings</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDFDEVICE_WDM_PRE_PO_FX_UNREGISTER_DEVICE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

