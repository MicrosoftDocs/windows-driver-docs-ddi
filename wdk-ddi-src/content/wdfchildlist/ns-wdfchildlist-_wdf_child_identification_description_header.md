---
UID: NS:wdfchildlist._WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
title: _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER (wdfchildlist.h)
description: The WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure is a header structure that must be the first member of every identification description structure.
old-location: wdf\wdf_child_identification_description_header.htm
tech.root: wdf
ms.assetid: 9bec95c9-785f-4578-a28a-6cffc986a3b9
ms.date: 02/26/2018
ms.keywords: "*PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, DFDeviceObjectChildListRef_543d7f3d-e182-4147-a1cb-62d39fdde4e3.xml, PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure pointer, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure, _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, kmdf.wdf_child_identification_description_header, wdf.wdf_child_identification_description_header, wdfchildlist/PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER"
f1_keywords:
 - "wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfchildlist.h
api_name:
- WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, *PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
---

# _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</b> structure is a header structure that must be the first member of every <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> structure.


## -struct-fields




### -field IdentificationDescriptionSize

The size, in bytes, of a driver-defined structure that contains device identification information.


## -remarks



To initialize a <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</b> structure, your driver should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>.

The value that the driver specifies for the <b>IdentificationDescriptionSize</b> member must match the value it specifies for the <b>IdentificationDescriptionSize</b> member in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_config">WDF_CHILD_LIST_CONFIG</a> structure.

Identification description structures are driver-defined. The driver must store the structure's size in the <b>IdentificationDescriptionSize</b> member. The size value must include the size of this header structure. For example, a driver might define an identification descriptor as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _IEEE_1394_CHILD_ID_DESCRIPTION {
  WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER  IdHeader;
 WCHAR  VendorName[32];
 WCHAR  ModelName[32];
 LONG  UnitSpecId; 
 LONG  UnitSoftwareVersion;
} IEEE_1394_CHILD_ID_DESCRIPTION, *PIEEE_1394_CHILD_ID_DESCRIPTION;</pre>
</td>
</tr>
</table></span></div>
To set the <b>IdentificationDescriptionSize</b> member for this address descriptor, the driver can use the following code:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IEEE_1394_CHILD_ID_DESCRIPTION ID_Description;
WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(&ID_Description,
                                                 sizeof(ID_Description));</pre>
</td>
</tr>
</table></span></div>
For more information about identification descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_list_config">WDF_CHILD_LIST_CONFIG</a>
 

 

