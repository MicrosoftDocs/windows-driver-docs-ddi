---
UID: NF:wdfchildlist.WDF_CHILD_LIST_CONFIG_INIT
title: WDF_CHILD_LIST_CONFIG_INIT function
author: windows-driver-content
description: The WDF_CHILD_LIST_CONFIG_INIT function initializes a WDF_CHILD_LIST_CONFIG structure.
old-location: wdf\wdf_child_list_config_init.htm
old-project: wdf
ms.assetid: d222f2f3-554f-43d5-97c5-9a56fdb42ec3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_b5fea12e-3e5b-4ec7-8e9d-0e385047cbdc.xml, WDF_CHILD_LIST_CONFIG_INIT, WDF_CHILD_LIST_CONFIG_INIT function, kmdf.wdf_child_list_config_init, wdf.wdf_child_list_config_init, wdfchildlist/WDF_CHILD_LIST_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_CHILD_LIST_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WDF_CHILD_LIST_CONFIG_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_LIST_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure.


## -parameters




### -param Config [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure.


### -param IdentificationDescriptionSize [in]

The size, in bytes, of each child device's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>. 


### -param EvtChildListCreateDevice [in]

The address of a driver-supplied <a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a> event callback function.


## -returns



None




## -remarks



The <b>WDF_CHILD_LIST_CONFIG_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure and sets the structure's <b>Size</b> member. Then it sets the <b>IdentificationDescriptionSize</b> and <b>EvtChildListCreateDevice</b> members to the specified values.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WDF_CHILD_LIST_CONFIG_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a>
 

 

