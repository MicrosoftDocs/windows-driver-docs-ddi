---
UID: NF:wdfchildlist.WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
title: WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function (wdfchildlist.h)
description: The WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function initializes a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure.
old-location: wdf\wdf_child_identification_description_header_init.htm
tech.root: wdf
ms.assetid: 5c0d7abf-05e3-45fc-b5a4-db6f79a94a87
ms.date: 02/26/2018
keywords: ["WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function"]
ms.keywords: DFDeviceObjectChildListRef_dbb576dd-7020-4c96-8f3a-568fd58f6cf5.xml, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function, kmdf.wdf_child_identification_description_header_init, wdf.wdf_child_identification_description_header_init, wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
f1_keywords:
 - "wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT"
 - "WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfchildlist.h
api_name:
- WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
targetos: Windows
req.typenames: 
---

# WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b> function initializes a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -parameters




### -param Header 
[out]
A pointer to a driver-allocated WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure.


### -param IdentificationDescriptionSize 
[in]
The size, in bytes, of a driver-defined structure that contains device identification information. For more information about specifying the size value, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>. 


## -remarks



The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b> function zeros the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure and sets the structure's <b>IdentificationDescriptionSize</b> member to the specified value.

For more information about child identification descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>
 

 

