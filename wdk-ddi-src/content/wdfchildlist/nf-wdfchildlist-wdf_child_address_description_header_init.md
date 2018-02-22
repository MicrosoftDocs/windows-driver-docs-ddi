---
UID: NF:wdfchildlist.WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
title: WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function
author: windows-driver-content
description: The WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function initializes a WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure.
old-location: wdf\wdf_child_address_description_header_init.htm
old-project: wdf
ms.assetid: acc56cb0-5f89-413f-9fdc-a051cc4947c0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.wdf_child_address_description_header_init, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function, wdfchildlist/WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT, DFDeviceObjectChildListRef_167489bc-617b-440a-a0b2-d5c346b4cf50.xml, WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT, kmdf.wdf_child_address_description_header_init
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfchildlist.h
apiname:
-	WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b> function initializes a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure.


## -syntax


````
VOID WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT(
  _Out_ PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER Header,
  _In_  ULONG                                 AddressDescriptionSize
);
````


## -parameters




### -param Header [out]

A pointer to a driver-allocated WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure.


### -param AddressDescriptionSize [in]

The size, in bytes, of a driver-defined structure that contains device address information. For more information about specifying the size value, see <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>.


## -returns



None




## -remarks



The <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b> function zeros the specified <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure and sets the structure's <b>AddressDescriptionSize</b> member to the specified value.

For more information about child address descriptions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

For a code example that uses <b>WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</b>, see <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrieveaddressdescription.md">WdfChildListRetrieveAddressDescription</a>.

<div class="code"></div>



## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

