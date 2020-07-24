---
UID: NF:wdfchildlist.WdfChildListAddOrUpdateChildDescriptionAsPresent
title: WdfChildListAddOrUpdateChildDescriptionAsPresent function (wdfchildlist.h)
description: The WdfChildListAddOrUpdateChildDescriptionAsPresent method adds a new child description to a list of children or updates an existing child description.
old-location: wdf\wdfchildlistaddorupdatechilddescriptionaspresent.htm
tech.root: wdf
ms.assetid: 10d169bc-4476-4d7f-8eeb-49941c12a7a0
ms.date: 02/26/2018
keywords: ["WdfChildListAddOrUpdateChildDescriptionAsPresent function"]
ms.keywords: DFDeviceObjectChildListRef_9e96421e-d818-4c2e-a46b-03db44980414.xml, WdfChildListAddOrUpdateChildDescriptionAsPresent, WdfChildListAddOrUpdateChildDescriptionAsPresent method, kmdf.wdfchildlistaddorupdatechilddescriptionaspresent, wdf.wdfchildlistaddorupdatechilddescriptionaspresent, wdfchildlist/WdfChildListAddOrUpdateChildDescriptionAsPresent
f1_keywords:
 - "wdfchildlist/WdfChildListAddOrUpdateChildDescriptionAsPresent"
 - "WdfChildListAddOrUpdateChildDescriptionAsPresent"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfChildListAddOrUpdateChildDescriptionAsPresent
targetos: Windows
req.typenames: 
---

# WdfChildListAddOrUpdateChildDescriptionAsPresent function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> method adds a new child description to a list of children or updates an existing child description.


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


### -param IdentificationDescription [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a child <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>.


### -param AddressDescription [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>. If an address description is not needed, this parameter can be <b>NULL</b>.


## -returns



<b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> returns STATUS_SUCCESS, or another NTSTATUS-typed status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The size of the identification description or address description was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_NAME_EXISTS</b></dt>
</dl>
</td>
<td width="60%">
A child with the supplied identification description already exists. In this case, the framework copies the supplied address description to the existing child.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A child description could be allocated.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



The <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> method searches the specified child list for a child that matches the supplied identification description. If a match is found, the framework updates the child's address description, if supplied, and returns STATUS_OBJECT_NAME_EXISTS. If no match is found, the framework creates a new child by using the supplied identification and address descriptions.

A driver can call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> to add or update a single child description. The framework immediately updates the child list and informs the Plug and Play (PnP) manager that changes have been made.

Alternatively, the driver can do the following:

<ol>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a> to prepare the child list for updating.

</li>
<li>
Call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> multiple times to add or update the child descriptions for all of the parent device's children.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a> to process changes to the child list.

</li>
</ol>
If the driver uses this alternative procedure, the framework waits until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a> before updating the child list and informing the PnP manager that changes have been made. When your driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>, the framework marks all previously reported devices as no longer being present. Therefore, the driver must call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> for all children, not just newly discovered children. 

At some time after a driver calls <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a> callback function so that the driver can create a device object by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example is based on code that the <a href="https://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample contains. The example adds child descriptions to a device's default child list. It retrieves switch settings that the driver previously stored in a device object's context space and then calls <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> for each switch that is set.

```cpp
PDEVICE_CONTEXT  pDeviceContext;
WDFCHILDLIST  list;
UCHAR  i;
NTSTATUS  status;

pDeviceContext = GetDeviceContext(Device);
list = WdfFdoGetDefaultChildList(Device);

WdfChildListBeginScan(list);
 
for (i = 0; i < RTL_BITS_OF(UCHAR); i++) {
    if (pDeviceContext->CurrentSwitchState & (1<<i)) {
        PDO_IDENTIFICATION_DESCRIPTION description;
        WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &description.Header,
                                                 sizeof(description)
                                                 );
        description.SwitchNumber = i; 
 
        status = WdfChildListAddOrUpdateChildDescriptionAsPresent(
                                                 list, 
                                                 &description.Header, 
                                                 NULL
                                                 );
        if (!NT_SUCCESS(status) && (status != STATUS_OBJECT_NAME_EXISTS)) {
            break;
        }
    }
}
WdfChildListEndScan(list);
```


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdogetdefaultchildlist">WdfFdoGetDefaultChildList</a>
 

 

