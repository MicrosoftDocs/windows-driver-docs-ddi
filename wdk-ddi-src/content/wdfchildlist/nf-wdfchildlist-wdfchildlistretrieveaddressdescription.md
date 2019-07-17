---
UID: NF:wdfchildlist.WdfChildListRetrieveAddressDescription
title: WdfChildListRetrieveAddressDescription function (wdfchildlist.h)
description: The WdfChildListRetrieveAddressDescription method locates a child device that has a specified identification description and retrieves the device's address description.
old-location: wdf\wdfchildlistretrieveaddressdescription.htm
tech.root: wdf
ms.assetid: 0c551de0-970a-4733-b904-27c40cf7b42f
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_bd30cd1e-b7ac-40cd-b96f-4071d08bafc1.xml, WdfChildListRetrieveAddressDescription, WdfChildListRetrieveAddressDescription method, kmdf.wdfchildlistretrieveaddressdescription, wdf.wdfchildlistretrieveaddressdescription, wdfchildlist/WdfChildListRetrieveAddressDescription
ms.topic: function
f1_keywords:
 - "wdfchildlist/WdfChildListRetrieveAddressDescription"
req.header: wdfchildlist.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfChildListRetrieveAddressDescription
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListRetrieveAddressDescription function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListRetrieveAddressDescription</b> method locates a child device that has a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> and retrieves the device's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>.


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param IdentificationDescription [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a driver-supplied child identification description.


### -param AddressDescription [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child address description. The framework fills in this description.


## -returns



<b>WdfChildListRetrieveAddressDescription</b> returns STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
An input parameter was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
No device matched the specified identification description.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The child list did not contain address descriptions, or the size of the address description that <i>AddressDescription</i> specified was incorrect.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example searches a child list for a child device whose identification description contains the value that is specified by <b>SomeValue</b>. If <b>WdfChildListRetrieveAddressDescription</b> locates the device, it retrieves the device's address description.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MY_IDENTIFICATION_DESCRIPTION  id;
MY_ADDRESS_DESCRIPTION  addrDescrip;

WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &id.Header,
                                                 sizeof(id)
                                                 );
WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT(
                                          &addrDescrip.Header,
                                          sizeof(addrDescrip)
                                          );

id.DeviceIdentifier = SomeValue;
status = WdfChildListRetrieveAddressDescription(
                                                list,
                                                &idDescrip.Header,
                                                &addrDescrip.Header
                                                );
if (!NT_SUCCESS(status) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_address_description_header_init">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>
 

 

