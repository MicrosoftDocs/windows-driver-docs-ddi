---
UID: NS:wdfchildlist._WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
title: "_WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER"
author: windows-driver-content
description: The WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure is a header structure that must be the first member of every identification description structure.
old-location: wdf\wdf_child_identification_description_header.htm
old-project: wdf
ms.assetid: 9bec95c9-785f-4578-a28a-6cffc986a3b9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: kmdf.wdf_child_identification_description_header, wdf.wdf_child_identification_description_header, _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, DFDeviceObjectChildListRef_543d7f3d-e182-4147-a1cb-62d39fdde4e3.xml, wdfchildlist/PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, *PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure pointer, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfchildlist.h
apiname:
-	WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER"
req.product: Windows 10 or later.
---

# _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</b> structure is a header structure that must be the first member of every <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> structure.


## -syntax


````
typedef struct _WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER {
  ULONG IdentificationDescriptionSize;
} WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER, *PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER;
````


## -struct-fields




### -field IdentificationDescriptionSize

The size, in bytes, of a driver-defined structure that contains device identification information.


## -remarks



To initialize a <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</b> structure, your driver should call <a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>.

The value that the driver specifies for the <b>IdentificationDescriptionSize</b> member must match the value it specifies for the <b>IdentificationDescriptionSize</b> member in its <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a> structure.

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
WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(&amp;ID_Description,
                                                 sizeof(ID_Description));</pre>
</td>
</tr>
</table></span></div>
For more information about identification descriptions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also

<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_config.md">WDF_CHILD_LIST_CONFIG</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

