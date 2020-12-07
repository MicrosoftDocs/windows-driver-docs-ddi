---
UID: NF:wdfchildlist.WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
title: WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function (wdfchildlist.h)
description: The WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function initializes a WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure.
old-location: wdf\wdf_child_address_description_header_init.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function"]
ms.keywords: DFDeviceObjectChildListRef_167489bc-617b-440a-a0b2-d5c346b4cf50.xml, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function, kmdf.wdf_child_address_description_header_init, wdf.wdf_child_address_description_header_init, wdfchildlist/WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
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
 - WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
 - wdfchildlist/WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfchildlist.h
api_name:
 - WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
---

# WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b> function initializes a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure.

## -parameters

### -param Header 

[out]
A pointer to a driver-allocated WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure.

### -param AddressDescriptionSize 

[in]
The size, in bytes, of a driver-defined structure that contains device address information. For more information about specifying the size value, see <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>.

## -remarks

The <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b> function zeros the specified <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure and sets the structure's <b>AddressDescriptionSize</b> member to the specified value.

For more information about child address descriptions, see <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b>, see <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrieveaddressdescription">WdfChildListRetrieveAddressDescription</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>
