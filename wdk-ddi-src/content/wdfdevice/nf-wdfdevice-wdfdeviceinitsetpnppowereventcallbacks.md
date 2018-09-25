---
UID: NF:wdfdevice.WdfDeviceInitSetPnpPowerEventCallbacks
title: WdfDeviceInitSetPnpPowerEventCallbacks function
author: windows-driver-content
description: The WdfDeviceInitSetPnpPowerEventCallbacks method registers a driver's Plug and Play and power management event callback functions.
old-location: wdf\wdfdeviceinitsetpnppowereventcallbacks.htm
tech.root: wdf
ms.assetid: ace53515-0e8a-487d-abf7-caaa09478ed5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_6a2f152e-b1ee-492e-a986-9c1ea925ff24.xml, WdfDeviceInitSetPnpPowerEventCallbacks, WdfDeviceInitSetPnpPowerEventCallbacks method, kmdf.wdfdeviceinitsetpnppowereventcallbacks, wdf.wdfdeviceinitsetpnppowereventcallbacks, wdfdevice/WdfDeviceInitSetPnpPowerEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceInitSetPnpPowerEventCallbacks
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

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param PnpPowerEventCallbacks [in]

A pointer to a caller-initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff552416">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



If your driver calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>, it must do so before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

For more information about calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552416">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and then calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_PNPPOWER_EVENT_CALLBACKS  pnpPowerCallbacks;

WDF_PNPPOWER_EVENT_CALLBACKS_INIT(&amp;pnpPowerCallbacks);
pnpPowerCallbacks.EvtDevicePrepareHardware = SerialEvtPrepareHardware;
pnpPowerCallbacks.EvtDeviceReleaseHardware = SerialEvtReleaseHardware;
pnpPowerCallbacks.EvtDeviceD0Entry = SerialEvtDeviceD0Entry;
pnpPowerCallbacks.EvtDeviceD0Exit = SerialEvtDeviceD0Exit;
WdfDeviceInitSetPnpPowerEventCallbacks(
                                       DeviceInit,
                                       &amp;pnpPowerCallbacks
                                       );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552418">WDF_PNPPOWER_EVENT_CALLBACKS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546774">WdfDeviceInitSetPowerPolicyEventCallbacks</a>
 

 

