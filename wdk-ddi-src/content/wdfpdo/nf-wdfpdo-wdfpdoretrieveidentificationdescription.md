---
UID: NF:wdfpdo.WdfPdoRetrieveIdentificationDescription
title: WdfPdoRetrieveIdentificationDescription function
author: windows-driver-content
description: The WdfPdoRetrieveIdentificationDescription method retrieves the identification description that is associated with a specified framework device object.
old-location: wdf\wdfpdoretrieveidentificationdescription.htm
old-project: wdf
ms.assetid: fac29ced-7acc-4c2a-ac8a-171b8dd1d45e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfPdoRetrieveIdentificationDescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfPdoRetrieveIdentificationDescription
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
req.product: Windows 10 or later.
---

# WdfPdoRetrieveIdentificationDescription function



## -description
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRetrieveIdentificationDescription</b> method retrieves the <a href="wdf.dynamic_enumeration#dynamic_child_descriptions#dynamic_child_descriptions">identification description</a> that is associated with a specified framework device object.



## -syntax

````
NTSTATUS WdfPdoRetrieveIdentificationDescription(
  _In_    WDFDEVICE                                    Device,
  _Inout_ PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


### -param IdentificationDescription [in, out]

A pointer to a caller-allocated buffer that will receive the identification description. The identification description must contain a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.


## -returns
If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The <i>Device</i> handle does not represent a PDO. 

<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The <i>Device</i> handle does not represent a device that was <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamically enumerated</a>, or if the <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure does not contain the correct buffer size.

 

The method might also return other<a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.

The following code example obtains a device's indentification description.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>
</dt>
<dt>
<a href="..\wdfpdo\nf-wdfpdo-wdfpdoretrieveaddressdescription.md">WdfPdoRetrieveAddressDescription</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoRetrieveIdentificationDescription method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

