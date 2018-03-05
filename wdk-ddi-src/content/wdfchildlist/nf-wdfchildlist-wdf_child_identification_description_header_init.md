---
UID: NF:wdfchildlist.WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
title: WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function
author: windows-driver-content
description: The WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function initializes a WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure.
old-location: wdf\wdf_child_identification_description_header_init.htm
old-project: wdf
ms.assetid: 5c0d7abf-05e3-45fc-b5a4-db6f79a94a87
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_dbb576dd-7020-4c96-8f3a-568fd58f6cf5.xml, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT, WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function, kmdf.wdf_child_identification_description_header_init, wdf.wdf_child_identification_description_header_init, wdfchildlist/WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
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
req.lib: NtosKrnl.exe
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
-	WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b> function initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -syntax


````
VOID WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
  _Out_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER Header,
  _In_  ULONG                                        IdentificationDescriptionSize
);
````


## -parameters




### -param Header [out]

A pointer to a driver-allocated WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER structure.


### -param IdentificationDescriptionSize [in]

The size, in bytes, of a driver-defined structure that contains device identification information. For more information about specifying the size value, see <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>. 


## -returns



None




## -remarks



The <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b> function zeros the specified <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure and sets the structure's <b>IdentificationDescriptionSize</b> member to the specified value.

For more information about child identification descriptions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent.md">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

