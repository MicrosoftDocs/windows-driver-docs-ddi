---
UID: NF:wdfdevice.WdfDeviceInitSetPnpPowerEventCallbacks
title: WdfDeviceInitSetPnpPowerEventCallbacks function (wdfdevice.h)
description: The WdfDeviceInitSetPnpPowerEventCallbacks method registers a driver's Plug and Play and power management event callback functions.
old-location: wdf\wdfdeviceinitsetpnppowereventcallbacks.htm
tech.root: wdf
ms.assetid: ace53515-0e8a-487d-abf7-caaa09478ed5
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_6a2f152e-b1ee-492e-a986-9c1ea925ff24.xml, WdfDeviceInitSetPnpPowerEventCallbacks, WdfDeviceInitSetPnpPowerEventCallbacks method, kmdf.wdfdeviceinitsetpnppowereventcallbacks, wdf.wdfdeviceinitsetpnppowereventcallbacks, wdfdevice/WdfDeviceInitSetPnpPowerEventCallbacks
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceInitSetPnpPowerEventCallbacks"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDeviceInitSetPnpPowerEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetPnpPowerEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceInitSetPnpPowerEventCallbacks</b> method registers a driver's Plug and Play and power management event callback functions.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param PnpPowerEventCallbacks [in]

A pointer to a caller-initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



If your driver calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_pnppower_event_callbacks">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and then calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>.

```cpp
WDF_PNPPOWER_EVENT_CALLBACKS  pnpPowerCallbacks;

WDF_PNPPOWER_EVENT_CALLBACKS_INIT(&pnpPowerCallbacks);
pnpPowerCallbacks.EvtDevicePrepareHardware = SerialEvtPrepareHardware;
pnpPowerCallbacks.EvtDeviceReleaseHardware = SerialEvtReleaseHardware;
pnpPowerCallbacks.EvtDeviceD0Entry = SerialEvtDeviceD0Entry;
pnpPowerCallbacks.EvtDeviceD0Exit = SerialEvtDeviceD0Exit;
WdfDeviceInitSetPnpPowerEventCallbacks(
                                       DeviceInit,
                                       &pnpPowerCallbacks
                                       );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdf_pnppower_event_callbacks_init">WDF_PNPPOWER_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks">WdfDeviceInitSetPowerPolicyEventCallbacks</a>
 

 

