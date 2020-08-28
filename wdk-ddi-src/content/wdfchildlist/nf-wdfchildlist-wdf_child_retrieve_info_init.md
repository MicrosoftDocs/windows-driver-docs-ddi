---
UID: NF:wdfchildlist.WDF_CHILD_RETRIEVE_INFO_INIT
title: WDF_CHILD_RETRIEVE_INFO_INIT function (wdfchildlist.h)
description: The WDF_CHILD_RETRIEVE_INFO_INIT function initializes a WDF_CHILD_RETRIEVE_INFO structure.
old-location: wdf\wdf_child_retrieve_info_init.htm
tech.root: wdf
ms.assetid: e41a656c-c507-45ca-a232-6926ace3c9d9
ms.date: 02/26/2018
keywords: ["WDF_CHILD_RETRIEVE_INFO_INIT function"]
ms.keywords: DFDeviceObjectChildListRef_f647d2ee-4714-49b9-9ba4-18488fd66628.xml, WDF_CHILD_RETRIEVE_INFO_INIT, WDF_CHILD_RETRIEVE_INFO_INIT function, kmdf.wdf_child_retrieve_info_init, wdf.wdf_child_retrieve_info_init, wdfchildlist/WDF_CHILD_RETRIEVE_INFO_INIT
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WDF_CHILD_RETRIEVE_INFO_INIT
 - wdfchildlist/WDF_CHILD_RETRIEVE_INFO_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdfchildlist.h
api_name:
 - WDF_CHILD_RETRIEVE_INFO_INIT
---

# WDF_CHILD_RETRIEVE_INFO_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_RETRIEVE_INFO_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure.

## -parameters

### -param Info 

[out]
A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure.

### -param IdentificationDescription 

[in]
A pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a>

