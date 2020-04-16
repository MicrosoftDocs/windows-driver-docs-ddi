---
UID: NF:wdfregistry.WdfRegistryClose
title: WdfRegistryClose function (wdfregistry.h)
description: The WdfRegistryClose method closes the registry key that is associated with a specified framework registry-key object and then deletes the registry-key object.
old-location: wdf\wdfregistryclose.htm
tech.root: wdf
ms.assetid: c97fe47d-bd6b-45d7-936b-3b46554e5093
ms.date: 02/26/2018
keywords: ["WdfRegistryClose function"]
ms.keywords: DFRegKeyObjectRef_31a198b2-e149-4fd4-951a-5fd03cf06555.xml, WdfRegistryClose, WdfRegistryClose method, kmdf.wdfregistryclose, wdf.wdfregistryclose, wdfregistry/WdfRegistryClose
f1_keywords:
 - "wdfregistry/WdfRegistryClose"
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
- WdfRegistryClose
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


## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After your driver has finished accessing a registry key, it must call <b>WdfRegistryClose</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>. Both of these methods close the registry key and delete the registry-key object. 

For more information about registry-key objects, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-registry-in-wdf-drivers">Using the Registry in Framework-Based Drivers</a>.


#### Examples

The following code example closes a registry key and deletes the registry-key object.

```cpp
WdfRegistryClose(Key);
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>
 

 

