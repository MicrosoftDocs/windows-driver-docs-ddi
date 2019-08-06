---
UID: NF:wdfdevice.WdfDeviceSetPnpCapabilities
title: WdfDeviceSetPnpCapabilities function (wdfdevice.h)
description: The WdfDeviceSetPnpCapabilities method reports a device's Plug and Play capabilities.
old-location: wdf\wdfdevicesetpnpcapabilities.htm
tech.root: wdf
ms.assetid: fba8bc7d-b776-44e8-a4bf-12de707f2e4f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_5f299c2e-344d-4213-a2fa-8266f056896c.xml, WdfDeviceSetPnpCapabilities, WdfDeviceSetPnpCapabilities method, kmdf.wdfdevicesetpnpcapabilities, wdf.wdfdevicesetpnpcapabilities, wdfdevice/WdfDeviceSetPnpCapabilities
ms.topic: function
f1_keywords:
 - "wdfdevice/WdfDeviceSetPnpCapabilities"
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
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
- WdfDeviceSetPnpCapabilities
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceSetPnpCapabilities function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceSetPnpCapabilities</b> method reports a device's Plug and Play capabilities.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PnpCapabilities [in]

A pointer to a driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver typically calls <b>WdfDeviceSetPnpCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_d0_entry">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nc-wdfdevice-evt_wdf_device_self_managed_io_init">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a>


</li>
</ul>
If more than one driver in the device's driver stack call <b>WdfDeviceSetPnpCapabilities</b>, the Plug and Play manager uses the values that are supplied by the driver that is highest in the stack. 


#### Examples

The following code examples initializes a WDF_DEVICE_PNP_CAPABILITIES structure and then calls <b>WdfDeviceSetPnpCapabilities</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_PNP_CAPABILITIES  pnpCaps;

WDF_DEVICE_PNP_CAPABILITIES_INIT(&pnpCaps);
pnpCaps.SurpriseRemovalOK = WdfTrue;

WdfDeviceSetPnpCapabilities(
                            device,
                            &pnpCaps
                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/ns-wdfdevice-_wdf_device_pnp_capabilities">WDF_DEVICE_PNP_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdf_device_pnp_capabilities_init">WDF_DEVICE_PNP_CAPABILITIES_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicesetpowercapabilities">WdfDeviceSetPowerCapabilities</a>
 

 

