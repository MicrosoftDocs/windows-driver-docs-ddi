---
UID: NF:wdfdevice.WdfDeviceSetPnpCapabilities
title: WdfDeviceSetPnpCapabilities function
description: The WdfDeviceSetPnpCapabilities method reports a device's Plug and Play capabilities.
old-location: wdf\wdfdevicesetpnpcapabilities.htm
tech.root: wdf
ms.assetid: fba8bc7d-b776-44e8-a4bf-12de707f2e4f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_5f299c2e-344d-4213-a2fa-8266f056896c.xml, WdfDeviceSetPnpCapabilities, WdfDeviceSetPnpCapabilities method, kmdf.wdfdevicesetpnpcapabilities, wdf.wdfdevicesetpnpcapabilities, wdfdevice/WdfDeviceSetPnpCapabilities
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfDeviceSetPnpCapabilities
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

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551257">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver typically calls <b>WdfDeviceSetPnpCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="https://msdn.microsoft.com/0cfabb0f-2d5e-4445-8683-d2916de5b549">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="https://msdn.microsoft.com/9dbc66db-ea94-4e6a-9618-00999a9dd641">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a>


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

WDF_DEVICE_PNP_CAPABILITIES_INIT(&amp;pnpCaps);
pnpCaps.SurpriseRemovalOK = WdfTrue;

WdfDeviceSetPnpCapabilities(
                            device,
                            &amp;pnpCaps
                            );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551257">WDF_DEVICE_PNP_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551259">WDF_DEVICE_PNP_CAPABILITIES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546901">WdfDeviceSetPowerCapabilities</a>
 

 

