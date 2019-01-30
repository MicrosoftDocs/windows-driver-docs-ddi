---
UID: NS:wdfchildlist._WDF_CHILD_ADDRESS_DESCRIPTION_HEADER
title: "_WDF_CHILD_ADDRESS_DESCRIPTION_HEADER" (wdfchildlist.h)
description: The WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure is a header structure that must be the first member of every address description structure.
old-location: wdf\wdf_child_address_description_header.htm
tech.root: wdf
ms.assetid: 2ea8041c-be80-42ff-9693-f6331508f6b2
ms.date: 02/26/2018
ms.keywords: "*PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER, DFDeviceObjectChildListRef_3fc67e2b-a0f5-4e03-a901-b2629e494157.xml, PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER, PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure pointer, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure, _WDF_CHILD_ADDRESS_DESCRIPTION_HEADER, kmdf.wdf_child_address_description_header, wdf.wdf_child_address_description_header, wdfchildlist/PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER, wdfchildlist/WDF_CHILD_ADDRESS_DESCRIPTION_HEADER"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_CHILD_ADDRESS_DESCRIPTION_HEADER
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_ADDRESS_DESCRIPTION_HEADER, *PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER
---

# _WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</b> structure is a header structure that must be the first member of every <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> structure.


## -struct-fields




### -field AddressDescriptionSize

The size, in bytes, of a driver-defined structure that contains device address information.


## -remarks



To initialize a <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551220">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</a>.

The value that the driver specifies for the <b>AddressDescriptionSize</b> member must match the value it specifies for the <b>AddressDescriptionSize</b> member in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a> structure.

Address description structures are driver-defined. The driver must store the structure's size in the <b>AddressDescriptionSize</b> member. The size value must include the size of this header structure. For example, a driver might define an address descriptor as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct _IEEE_1394_CHILD_ADDRESS_DESCRIPTION {
  WDF_CHILD_ADDRESS_DESCRIPTION_HEADER  AddressHeader;
  //
  // Current bus generation
  //
  ULONG Generation;
} IEEE_1394_CHILD_ADDRESS_DESCRIPTION, *PIEEE_1394_CHILD_ADDRESS_DESCRIPTION;</pre>
</td>
</tr>
</table></span></div>
To set the <b>AddressDescriptionSize</b> member for this address descriptor, the driver can use the following code:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IEEE_1394_CHILD_ADDRESS_DESCRIPTION Addr_Description;
WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT (&amp;Addr_Description, 
                                           sizeof(Addr_Description));</pre>
</td>
</tr>
</table></span></div>
For more information about address descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551220">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551227">WDF_CHILD_LIST_CONFIG</a>
 

 

