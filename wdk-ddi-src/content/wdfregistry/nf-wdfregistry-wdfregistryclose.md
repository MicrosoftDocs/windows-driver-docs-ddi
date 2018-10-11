---
UID: NF:wdfregistry.WdfRegistryClose
title: WdfRegistryClose function
author: windows-driver-content
description: The WdfRegistryClose method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.
old-location: wdf\wdfregistryclose.htm
tech.root: wdf
ms.assetid: c97fe47d-bd6b-45d7-936b-3b46554e5093
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFRegKeyObjectRef_31a198b2-e149-4fd4-951a-5fd03cf06555.xml, WdfRegistryClose, WdfRegistryClose method, kmdf.wdfregistryclose, wdf.wdfregistryclose, wdfregistry/WdfRegistryClose
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfregistry.h
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
req.irql: PASSIVE_LEVEL
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
-	WdfRegistryClose
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfRegistryClose function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRegistryClose</b> method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.


## -parameters




### -param Key [in]

A handle to a registry-key object that represents an opened registry key.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After your driver has finished accessing a registry key, it must call <b>WdfRegistryClose</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>. Both of these methods close the registry key and delete the registry-key object. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example closes a registry key and deletes the registry-key object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfRegistryClose(Key);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548734">WdfObjectDelete</a>
 

 

