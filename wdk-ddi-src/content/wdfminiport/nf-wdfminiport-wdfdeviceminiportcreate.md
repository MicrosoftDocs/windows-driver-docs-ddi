---
UID: NF:wdfminiport.WdfDeviceMiniportCreate
title: WdfDeviceMiniportCreate function
author: windows-driver-content
description: The WdfDeviceMiniportCreate method creates a framework device object that a miniport driver can use.
old-location: wdf\wdfdeviceminiportcreate.htm
tech.root: wdf
ms.assetid: d74dedbd-f418-4ea3-ae76-c0da9c5f2fb9
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_18104589-c58d-4e8b-af91-c6620b3772e9.xml, WdfDeviceMiniportCreate, WdfDeviceMiniportCreate method, kmdf.wdfdeviceminiportcreate, wdf.wdfdeviceminiportcreate, wdfminiport/WdfDeviceMiniportCreate
ms.topic: function
req.header: wdfminiport.h
req.include-header: Wdfminiport.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceMiniportCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceMiniportCreate function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfDeviceMiniportCreate</b> method creates a framework device object that a miniport driver can use.


## -parameters




### -param Driver [in]

A handle to the driver's framework driver object, obtained by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547175">WdfDriverCreate</a>.


### -param Attributes [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param DeviceObject [in]

A pointer to a WDM <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents the functional device object (FDO) for the miniport driver.


### -param AttachedDeviceObject [in, optional]

A pointer to a WDM DEVICE_OBJECT structure that represents the next-lower device object in the device stack.


### -param Pdo [in, optional]

A pointer to a WDM DEVICE_OBJECT structure that represents the physical device object (PDO) for the device.


### -param Device [out]

A pointer to a location that receives a handle to the new framework device object.


## -returns



If the <b>WdfDeviceMiniportCreate</b> method encounters no errors, it returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A device object could not be allocated.

</td>
</tr>
</table>
 

For a list of other return values that <b>WdfDeviceMiniportCreate</b> can return, see <a href="https://msdn.microsoft.com/f5345c88-1c3a-4b32-9c93-c252713f7641">Framework Object Creation Errors</a>.

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



If your miniport driver uses the framework, the miniport driver should call <b>WdfDeviceMiniportCreate</b> when its port driver informs it that a device is available. Miniport drivers do not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

Your miniport driver might receive its <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers from its port driver. For example, an NDIS miniport driver can obtain these pointers by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563592">NdisMGetDeviceProperty</a>.

The following restrictions apply to framework device objects that a miniport driver obtains by calling <b>WdfDeviceMiniportCreate</b>:

<ul>
<li>
The device that the device object represents must support Plug and Play.

</li>
<li>
The device object does not support any of the device object's event callback functions. Therefore, the port driver must handle all Plug and Play (PnP) and power management operations. 

</li>
<li>
The device object handle cannot be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551193">WdfWmiProviderCreate</a>, so the port driver must provide any required support for Windows Management Instrumentation (WMI).

</li>
<li>
The device object handle cannot be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547401">WdfIoQueueCreate</a>, so the framework does not support I/O queues for miniport drivers.

</li>
<li>
The device object handle cannot be passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff547345">WdfInterruptCreate</a>, so the framework does not support interrupt objects for miniport drivers.

</li>
<li>
The device object handle cannot be passed to any general framework device object methods except <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546942">WdfDeviceWdmGetDeviceObject</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546934">WdfDeviceWdmGetAttachedDevice</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff546946">WdfDeviceWdmGetPhysicalDevice</a>.

</li>
<li>
The device object handle cannot be passed to any <a href="https://msdn.microsoft.com/library/windows/hardware/dn265631">framework FDO methods</a> except <a href="https://msdn.microsoft.com/library/windows/hardware/ff547289">WdfFdoQueryForInterface</a>.

</li>
<li>
The device object handle cannot be passed to any <a href="https://msdn.microsoft.com/library/windows/hardware/dn265631">framework PDO methods</a> or to <a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>, so the miniport driver cannot be a bus driver.

</li>
<li>
The driver must eventually call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a> to delete the device object that <b>WdfDeviceMiniportCreate</b> creates.

</li>
</ul>
Framework device objects that <b>WdfDeviceMiniportCreate</b> create can be used as a parent object for any subsequently created framework object. 

In order to send I/O requests to I/O targets, the miniport driver might pass the device object handle to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546017">WdfDeviceGetIoTarget</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.

The miniport driver can pass the device object handle to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546983">WdfDmaEnablerCreate</a> if the device supports DMA operations.

For more information about miniport drivers, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-kmdf-miniport-drivers">Using Kernel-Mode Driver Framework with Miniport Drivers</a>.


#### Examples

The following code example calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff563592">NdisMGetDeviceProperty</a> to obtain <i>DeviceObject</i>, <i>AttachedDeviceObject</i>, and <i>PDO</i> pointers; initializes the device object's context space, and creates a miniport device object. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  ObjectAttributes;

NdisMGetDeviceProperty(
                       MiniportAdapterHandle,
                       &amp;Adapter-&gt;Pdo,
                       &amp;Adapter-&gt;Fdo,
                       &amp;Adapter-&gt;NextDeviceObject,
                       NULL,
                       NULL
                       );
WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &amp;ObjectAttributes,
                                        WDF_DEVICE_INFO
                                        );
ntStatus = WdfDeviceMiniportCreate(
                                   WdfGetDriver(),
                                   &amp;ObjectAttributes,
                                   Adapter-&gt;Fdo,
                                   Adapter-&gt;NextDeviceObject,
                                   Adapter-&gt;Pdo,
                                   &amp;Adapter-&gt;WdfDevice
                                   );
if (!NT_SUCCESS (ntStatus)) {
    Status = NDIS_STATUS_FAILURE;
    break;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552404">WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547193">WdfDriverMiniportUnload</a>
 

 

