---
UID: NF:wdfdevice.WdfDeviceInitSetPnpPowerEventCallbacks
title: WdfDeviceInitSetPnpPowerEventCallbacks function
author: windows-driver-content
description: The WdfDeviceInitSetPnpPowerEventCallbacks method registers a driver's Plug and Play and power management event callback functions.
old-location: wdf\wdfdeviceinitsetpnppowereventcallbacks.htm
old-project: wdf
ms.assetid: ace53515-0e8a-487d-abf7-caaa09478ed5
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFDeviceObjectGeneralRef_6a2f152e-b1ee-492e-a986-9c1ea925ff24.xml, E, I, P, S, W, WdfDeviceInitSetPnpPowerEventCallbacks, WdfDeviceInitSetPnpPowerEventCallbacks method, a, b, c, d, e, f, i, k, kmdf.wdfdeviceinitsetpnppowereventcallbacks, l, n, o, p, r, s, t, v, w, wdf.wdfdeviceinitsetpnppowereventcallbacks, wdfdevice/WdfDeviceInitSetPnpPowerEventCallbacks"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfDeviceInitSetPnpPowerEventCallbacks
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPnpPowerEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceInitSetPnpPowerEventCallbacks</b> method registers a driver's Plug and Play and power management event callback functions.


## -syntax


````
VOID WdfDeviceInitSetPnpPowerEventCallbacks(
  _In_ PWDFDEVICE_INIT               DeviceInit,
  _In_ PWDF_PNPPOWER_EVENT_CALLBACKS PnpPowerEventCallbacks
);
````


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param PnpPowerEventCallbacks [in]

A pointer to a caller-initialized <a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



If your driver calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.


#### Examples

The following code example initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_pnppower_event_callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and then calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>.

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

<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>



<a href="..\wdfdevice\nf-wdfdevice-wdf_pnppower_event_callbacks_init.md">WDF_PNPPOWER_EVENT_CALLBACKS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetPnpPowerEventCallbacks method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

