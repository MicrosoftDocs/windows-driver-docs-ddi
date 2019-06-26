---
UID: NF:wdfdevice.WdfDeviceWdmGetDeviceObject
title: WdfDeviceWdmGetDeviceObject function (wdfdevice.h)
description: The WdfDeviceWdmGetDeviceObject method returns the Windows Driver Model (WDM) device object that is associated with a specified framework device object.
old-location: wdf\wdfdevicewdmgetdeviceobject.htm
tech.root: wdf
ms.assetid: 87a427ae-5c1e-4975-a48f-80c3549a3564
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_b145d3cd-578a-4be9-80d1-b260f5693b3d.xml, WdfDeviceWdmGetDeviceObject, WdfDeviceWdmGetDeviceObject method, kmdf.wdfdevicewdmgetdeviceobject, wdf.wdfdevicewdmgetdeviceobject, wdfdevice/WdfDeviceWdmGetDeviceObject
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfDeviceWdmGetDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceWdmGetDeviceObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceWdmGetDeviceObject</b> method returns the Windows Driver Model (WDM) device object that is associated with a specified framework device object.


## -parameters




### -param Device

<p>A handle to a framework device object.</p>




## -returns



<b>WdfDeviceWdmGetDeviceObject</b> returns a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



The pointer that the <b>WdfDeviceWdmGetDeviceObject</b> method returns is valid until the framework device object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework device object, the pointer is valid until the callback function returns.


#### Examples

The following code example creates a tracing message that contains pointers to the WDM device objects that represent a device's PDO and FDO.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>TraceEvents(
            TRACE_LEVEL_INFORMATION,
            AMCC_TRACE_INIT,
            "PDO 0x%p, FDO 0x%p",
            WdfDeviceWdmGetPhysicalDevice(device),
            WdfDeviceWdmGetDeviceObject(device)
            );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicewdmgetphysicaldevice">WdfDeviceWdmGetPhysicalDevice</a>
 

 

