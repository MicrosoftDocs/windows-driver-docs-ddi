---
UID: NF:wdfpdo.WdfPdoAddEjectionRelationsPhysicalDevice
title: WdfPdoAddEjectionRelationsPhysicalDevice function (wdfpdo.h)
description: The WdfPdoAddEjectionRelationsPhysicalDevice method indicates that a specified device is ejected when another specified device is ejected.
old-location: wdf\wdfpdoaddejectionrelationsphysicaldevice.htm
tech.root: wdf
ms.assetid: 23a9ab2a-be8e-40ff-8654-adf170adc6f2
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_c13c9c42-f704-4042-b70d-952ddb8a27b8.xml, WdfPdoAddEjectionRelationsPhysicalDevice, WdfPdoAddEjectionRelationsPhysicalDevice method, kmdf.wdfpdoaddejectionrelationsphysicaldevice, wdf.wdfpdoaddejectionrelationsphysicaldevice, wdfpdo/WdfPdoAddEjectionRelationsPhysicalDevice
ms.topic: function
req.header: wdfpdo.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfPdoAddEjectionRelationsPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoAddEjectionRelationsPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoAddEjectionRelationsPhysicalDevice</b> method indicates that a specified device is ejected when another specified device is ejected.


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PhysicalDevice [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## -returns



If the operation succeeds, the method returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory allocation failed.

</td>
</tr>
</table>
 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <i>PhysicalDevice</i> parameter points to a PDO of a device that is ejected when the device that is identified by <i>Device</i> is ejected. Typically, both devices are controlled by the calling driver. Do not report the child devices of <i>Device</i> because when the PnP manager ejects a parent device, it also ejects the device's children.

For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


#### Examples

The following code example adds a device that the <b>pPhysicalDeviceObject</b> structure represents to the list of devices that are ejected when the device that <b>device</b> specifies is ejected.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDEVICE_OBJECT  pPhysicalDeviceObject;
NTSTATUS  status;
...
status = WdfPdoAddEjectionRelationsPhysicalDevice(
 device,
 pPhysicalDeviceObject
                                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548771">WdfPdoClearEjectionRelationsDevices</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548814">WdfPdoRemoveEjectionRelationsPhysicalDevice</a>
 

 

