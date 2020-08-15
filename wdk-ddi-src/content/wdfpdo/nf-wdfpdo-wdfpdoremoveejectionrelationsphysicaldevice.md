---
UID: NF:wdfpdo.WdfPdoRemoveEjectionRelationsPhysicalDevice
title: WdfPdoRemoveEjectionRelationsPhysicalDevice function (wdfpdo.h)
description: The WdfPdoRemoveEjectionRelationsPhysicalDevice method removes a specified device from the list of devices that must be ejected when another specified device is ejected.
old-location: wdf\wdfpdoremoveejectionrelationsphysicaldevice.htm
tech.root: wdf
ms.assetid: d224b93b-4c3e-4e14-bc5d-404cb703752c
ms.date: 02/26/2018
keywords: ["WdfPdoRemoveEjectionRelationsPhysicalDevice function"]
ms.keywords: DFDeviceObjectFdoPdoRef_7a599cb2-dbb7-4fce-b04b-1b92638e17de.xml, WdfPdoRemoveEjectionRelationsPhysicalDevice, WdfPdoRemoveEjectionRelationsPhysicalDevice method, kmdf.wdfpdoremoveejectionrelationsphysicaldevice, wdf.wdfpdoremoveejectionrelationsphysicaldevice, wdfpdo/WdfPdoRemoveEjectionRelationsPhysicalDevice
f1_keywords:
 - "wdfpdo/WdfPdoRemoveEjectionRelationsPhysicalDevice"
 - "WdfPdoRemoveEjectionRelationsPhysicalDevice"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoRemoveEjectionRelationsPhysicalDevice
targetos: Windows
req.typenames: 
---

# WdfPdoRemoveEjectionRelationsPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> method removes a specified device from the list of devices that must be ejected when another specified device is ejected. 


## -parameters




### -param Device 
[in]
A handle to a framework device object.


### -param PhysicalDevice 
[in]
A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents a physical device object (PDO).


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




The <i>PhysicalDevice</i> parameter points to a PDO of a device that <b>WdfPdoRemoveEjectionRelationsPhysicalDevice</b> removes from the list of devices that must be ejected when the device represented by the <i>Device</i> parameter is ejected.

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-ejectable-devices">Supporting Ejectable Devices</a>.


#### Examples

The following code example removes the device that the <b>pPhysicalDeviceObject</b> structure represents from the list of devices that are ejected when the device that <b>device</b> specifies is ejected.

```cpp
PDEVICE_OBJECT  pPhysicalDeviceObject;
NTSTATUS  status;
...
status = WdfPdoRemoveEjectionRelationsPhysicalDevice(
                                                     device,
                                                     pPhysicalDeviceObject
                                                     );
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoaddejectionrelationsphysicaldevice">WdfPdoAddEjectionRelationsPhysicalDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoclearejectionrelationsdevices">WdfPdoClearEjectionRelationsDevices</a>
 

 

