---
UID: NF:wdfpdo.WdfPdoRetrieveIdentificationDescription
title: WdfPdoRetrieveIdentificationDescription function (wdfpdo.h)
description: The WdfPdoRetrieveIdentificationDescription method retrieves the identification description that is associated with a specified framework device object.
old-location: wdf\wdfpdoretrieveidentificationdescription.htm
tech.root: wdf
ms.assetid: fac29ced-7acc-4c2a-ac8a-171b8dd1d45e
ms.date: 02/26/2018
keywords: ["WdfPdoRetrieveIdentificationDescription function"]
ms.keywords: DFDeviceObjectFdoPdoRef_fe883ca1-8b36-4ac1-b7ff-8c38bf098148.xml, WdfPdoRetrieveIdentificationDescription, WdfPdoRetrieveIdentificationDescription method, kmdf.wdfpdoretrieveidentificationdescription, wdf.wdfpdoretrieveidentificationdescription, wdfpdo/WdfPdoRetrieveIdentificationDescription
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfPdoRetrieveIdentificationDescription
 - wdfpdo/WdfPdoRetrieveIdentificationDescription
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfPdoRetrieveIdentificationDescription
---

# WdfPdoRetrieveIdentificationDescription function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoRetrieveIdentificationDescription</b> method retrieves the <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> that is associated with a specified framework device object.

## -parameters

### -param Device 

[in]
A handle to a framework device object that represents the device's physical device object (PDO).

### -param IdentificationDescription 

[in, out]
A pointer to a caller-allocated buffer that will receive the identification description. The identification description must contain a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a PDO. 


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The <i>Device</i> handle does not represent a device that was <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">dynamically enumerated</a>, or if the <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure does not contain the correct buffer size.

</td>
</tr>
</table>
 

The method might also return other<a href="/windows-hardware/drivers/kernel/ntstatus-values"> NTSTATUS values</a>.

A system bug check occurs if the driver supplies an invalid object handle.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfpdo/nf-wdfpdo-wdfpdoretrieveaddressdescription">WdfPdoRetrieveAddressDescription</a>