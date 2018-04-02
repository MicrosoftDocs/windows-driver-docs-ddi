---
UID: NF:wdfpdo.WdfPdoClearEjectionRelationsDevices
title: WdfPdoClearEjectionRelationsDevices function
author: windows-driver-content
description: The WdfPdoClearEjectionRelationsDevices method removes all devices from the list of devices that must be ejected when a specified device is ejected.
old-location: wdf\wdfpdoclearejectionrelationsdevices.htm
old-project: wdf
ms.assetid: 09154884-130d-47aa-be00-08a3a4da6f22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_ddbc7fa5-d0c0-4074-901e-bc7a8ea50fa4.xml, WdfPdoClearEjectionRelationsDevices, WdfPdoClearEjectionRelationsDevices method, kmdf.wdfpdoclearejectionrelationsdevices, wdf.wdfpdoclearejectionrelationsdevices, wdfpdo/WdfPdoClearEjectionRelationsDevices
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfPdoClearEjectionRelationsDevices
product:
- Windows
targetos: Windows
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoClearEjectionRelationsDevices function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoClearEjectionRelationsDevices</b> method removes all devices from the list of devices that must be ejected when a specified device is ejected. 


## -parameters




### -param Device [in]

A handle to a framework device object.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


#### Examples

The following code example clears the specified device's list of ejection relations.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfPdoClearEjectionRelationsDevices(device); </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548770">WdfPdoAddEjectionRelationsPhysicalDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548814">WdfPdoRemoveEjectionRelationsPhysicalDevice</a>
 

 

