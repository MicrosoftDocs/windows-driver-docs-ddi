---
UID: NF:wdfpdo.WdfPdoRemoveEjectionRelationsPhysicalDevice
title: WdfPdoRemoveEjectionRelationsPhysicalDevice function
author: windows-driver-content
description: The WdfPdoRemoveEjectionRelationsPhysicalDevice method removes a specified device from the list of devices that must be ejected when another specified device is ejected.
old-location: wdf\wdfpdoremoveejectionrelationsphysicaldevice.htm
tech.root: wdf
ms.assetid: d224b93b-4c3e-4e14-bc5d-404cb703752c
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_7a599cb2-dbb7-4fce-b04b-1b92638e17de.xml, WdfPdoRemoveEjectionRelationsPhysicalDevice, WdfPdoRemoveEjectionRelationsPhysicalDevice method, kmdf.wdfpdoremoveejectionrelationsphysicaldevice, wdf.wdfpdoremoveejectionrelationsphysicaldevice, wdfpdo/WdfPdoRemoveEjectionRelationsPhysicalDevice
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
-	WdfPdoRemoveEjectionRelationsPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoRemoveEjectionRelationsPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> method removes a specified device from the list of devices that must be ejected when another specified device is ejected. 


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param PhysicalDevice [in]

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <i>PhysicalDevice</i> parameter points to a PDO of a device that <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> removes from the list of devices that must be ejected when the device represented by the <i>Device</i> parameter is ejected.

For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


#### Examples

The following code example removes the device that the <b>pPhysicalDeviceObject</b> structure represents from the list of devices that are ejected when the device that <b>device</b> specifies is ejected.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDEVICE_OBJECT  pPhysicalDeviceObject;
NTSTATUS  status;
...
status = WdfPdoRemoveEjectionRelationsPhysicalDevice(
                                                     device,
                                                     pPhysicalDeviceObject
                                                     );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548770">WdfPdoAddEjectionRelationsPhysicalDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548771">WdfPdoClearEjectionRelationsDevices</a>
 

 

