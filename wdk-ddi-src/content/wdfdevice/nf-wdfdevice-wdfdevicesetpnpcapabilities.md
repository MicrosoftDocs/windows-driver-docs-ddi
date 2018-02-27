---
UID: NF:wdfdevice.WdfDeviceSetPnpCapabilities
title: WdfDeviceSetPnpCapabilities function
author: windows-driver-content
description: The WdfDeviceSetPnpCapabilities method reports a device's Plug and Play capabilities.
old-location: wdf\wdfdevicesetpnpcapabilities.htm
old-project: wdf
ms.assetid: fba8bc7d-b776-44e8-a4bf-12de707f2e4f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_5f299c2e-344d-4213-a2fa-8266f056896c.xml, WdfDeviceSetPnpCapabilities, WdfDeviceSetPnpCapabilities method, kmdf.wdfdevicesetpnpcapabilities, wdf.wdfdevicesetpnpcapabilities, wdfdevice/WdfDeviceSetPnpCapabilities
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
-	WdfDeviceSetPnpCapabilities
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetPnpCapabilities function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetPnpCapabilities</b> method reports a device's Plug and Play capabilities.


## -syntax


````
VOID WdfDeviceSetPnpCapabilities(
  _In_ WDFDEVICE                    Device,
  _In_ PWDF_DEVICE_PNP_CAPABILITIES PnpCapabilities
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PnpCapabilities [in]

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_capabilities.md">WDF_DEVICE_PNP_CAPABILITIES</a> structure.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



A driver typically calls <b>WdfDeviceSetPnpCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>


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

<a href="..\wdfdevice\nf-wdfdevice-wdf_device_pnp_capabilities_init.md">WDF_DEVICE_PNP_CAPABILITIES_INIT</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetpowercapabilities.md">WdfDeviceSetPowerCapabilities</a>



<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_pnp_capabilities.md">WDF_DEVICE_PNP_CAPABILITIES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetPnpCapabilities method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

