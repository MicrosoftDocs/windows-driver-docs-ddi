---
UID: NF:wdfdevice.WdfDeviceInitSetPowerPolicyEventCallbacks
title: WdfDeviceInitSetPowerPolicyEventCallbacks function (wdfdevice.h)
description: The WdfDeviceInitSetPowerPolicyEventCallbacks method registers a driver's power policy event callback functions.
old-location: wdf\wdfdeviceinitsetpowerpolicyeventcallbacks.htm
tech.root: wdf
ms.assetid: ae74d58c-3b36-4298-aa6f-4c272e7ff61c
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_7a73b769-9408-4349-b269-53dff2261d3d.xml, WdfDeviceInitSetPowerPolicyEventCallbacks, WdfDeviceInitSetPowerPolicyEventCallbacks method, kmdf.wdfdeviceinitsetpowerpolicyeventcallbacks, wdf.wdfdeviceinitsetpowerpolicyeventcallbacks, wdfdevice/WdfDeviceInitSetPowerPolicyEventCallbacks
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI, PdoDeviceInitAPI
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
- WdfDeviceInitSetPowerPolicyEventCallbacks
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetPowerPolicyEventCallbacks function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceInitSetPowerPolicyEventCallbacks</b> method registers a driver's power policy event callback functions.


## -parameters




### -param DeviceInit [in]

A caller-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


### -param PowerPolicyEventCallbacks [in]

A pointer to a caller-initialized <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure.


## -returns



None




## -remarks



If your driver calls <b>WdfDeviceInitSetPowerPolicyEventCallbacks</b>, it must do so before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about <b>WdfDeviceInitSetPowerPolicyEventCallbacks</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/power-policy-ownership">Power Policy Ownership</a>.


#### Examples

The following code example initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_power_policy_event_callbacks">WDF_POWER_POLICY_EVENT_CALLBACKS</a> structure and then calls <b>WdfDeviceInitSetPowerPolicyEventCallbacks</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_POWER_POLICY_EVENT_CALLBACKS powerPolicyCallbacks;

WDF_POWER_POLICY_EVENT_CALLBACKS_INIT(&powerPolicyCallbacks);
powerPolicyCallbacks.EvtDeviceArmWakeFromS0 = PciDrvEvtDeviceWakeArmS0;
powerPolicyCallbacks.EvtDeviceDisarmWakeFromS0 = PciDrvEvtDeviceWakeDisarmS0;
powerPolicyCallbacks.EvtDeviceWakeFromS0Triggered = PciDrvEvtDeviceWakeTriggeredS0;
powerPolicyCallbacks.EvtDeviceArmWakeFromSx = PciDrvEvtDeviceWakeArmSx;
powerPolicyCallbacks.EvtDeviceDisarmWakeFromSx = PciDrvEvtDeviceWakeDisarmSx;
powerPolicyCallbacks.EvtDeviceWakeFromSxTriggered = PciDrvEvtDeviceWakeTriggeredSx;
WdfDeviceInitSetPowerPolicyEventCallbacks(
                                          DeviceInit,
                                          &powerPolicyCallbacks
                                          );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdf_power_policy_event_callbacks_init">WDF_POWER_POLICY_EVENT_CALLBACKS_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>
 

 

