---
UID: NC:storport.HW_FREE_ADAPTER_RESOURCES
title: HW_FREE_ADAPTER_RESOURCES
author: windows-driver-content
description: The HwStorFreeAdapterResources callback routine allows the Storport virtual miniport driver to free resources when the virtual adapter is being removed. This is the last callback routine for the adapter.
old-location: storage\hwstorfreeadapterresources.htm
old-project: storage
ms.assetid: 2f12aab4-ca6e-473b-a342-2881c4a7b133
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.hwstorfreeadapterresources, HwStorFreeAdapterResources routine [Storage Devices], HwStorFreeAdapterResources, HW_FREE_ADAPTER_RESOURCES, HW_FREE_ADAPTER_RESOURCES, storport/HwStorFreeAdapterResources, storvmini_88adb6fa-10a8-4ee7-90d3-881564ed5cfd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Storport.h
apiname:
-	HwStorFreeAdapterResources
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER"
req.product: Windows 10 or later.
---

# HW_FREE_ADAPTER_RESOURCES callback


## -description


The <b>HwStorFreeAdapterResources</b> callback routine allows the Storport virtual miniport driver to free resources when the virtual adapter is being removed. This is the last callback routine for the adapter.


## -prototype


````
HW_FREE_ADAPTER_RESOURCES HwStorFreeAdapterResources;

VOID HwStorFreeAdapterResources(
   IN PVOID DeviceExtension
)
{ ... }
````


## -parameters




### -param DeviceExtension

A pointer to the virtual miniport driver's per-adapter storage area.


## -returns


None



## -remarks


The name <b>HwStorFreeAdapterResources</b> is  placeholder text for the actual routine name. The actual prototype of this routine is defined in Storport.h as follows:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*PHW_FREE_ADAPTER_RESOURCES) (
  IN PVOID  DeviceExtension
  );</pre>
</td>
</tr>
</table></span></div>The port driver calls the Storport virtual miniport's <b>HwStorFreeAdapterResources</b> at PASSIVE_LEVEL. 


