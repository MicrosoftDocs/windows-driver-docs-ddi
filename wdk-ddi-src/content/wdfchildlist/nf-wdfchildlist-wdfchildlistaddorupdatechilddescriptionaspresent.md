---
UID: NF:wdfchildlist.WdfChildListAddOrUpdateChildDescriptionAsPresent
title: WdfChildListAddOrUpdateChildDescriptionAsPresent function
author: windows-driver-content
description: The WdfChildListAddOrUpdateChildDescriptionAsPresent method adds a new child description to a list of children or updates an existing child description.
old-location: wdf\wdfchildlistaddorupdatechilddescriptionaspresent.htm
old-project: wdf
ms.assetid: 10d169bc-4476-4d7f-8eeb-49941c12a7a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectChildListRef_9e96421e-d818-4c2e-a46b-03db44980414.xml, WdfChildListAddOrUpdateChildDescriptionAsPresent, WdfChildListAddOrUpdateChildDescriptionAsPresent method, kmdf.wdfchildlistaddorupdatechilddescriptionaspresent, wdf.wdfchildlistaddorupdatechilddescriptionaspresent, wdfchildlist/WdfChildListAddOrUpdateChildDescriptionAsPresent
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfChildListAddOrUpdateChildDescriptionAsPresent
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListAddOrUpdateChildDescriptionAsPresent function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> method adds a new child description to a list of children or updates an existing child description.


## -syntax


````
NTSTATUS WdfChildListAddOrUpdateChildDescriptionAsPresent(
  _In_     WDFCHILDLIST                                 ChildList,
  _In_     PWDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER IdentificationDescription,
  _In_opt_ PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER        AddressDescription
);
````


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


### -param IdentificationDescription [in]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a child <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>.


### -param AddressDescription [in, optional]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>. If an address description is not needed, this parameter can be <b>NULL</b>.


## -returns



<b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> returns STATUS_SUCCESS, or another NTSTATUS-typed status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



The <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> method searches the specified child list for a child that matches the supplied identification description. If a match is found, the framework updates the child's address description, if supplied, and returns STATUS_OBJECT_NAME_EXISTS. If no match is found, the framework creates a new child by using the supplied identification and address descriptions.

A driver can call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> to add or update a single child description. The framework immediately updates the child list and informs the Plug and Play (PnP) manager that changes have been made.

Alternatively, the driver can do the following:

<ol>
<li>
Call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a> to prepare the child list for updating.

</li>
<li>
Call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> multiple times to add or update the child descriptions for all of the parent device's children.

</li>
<li>
Call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a> to process changes to the child list.

</li>
</ol>
If the driver uses this alternative procedure, the framework waits until the driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a> before updating the child list and informing the PnP manager that changes have been made. When your driver calls <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>, the framework marks all previously reported devices as no longer being present. Therefore, the driver must call <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> for all children, not just newly discovered children. 

At some time after a driver calls <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b>, the framework calls the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> callback function so that the driver can create a device object by calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example is based on code that the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample contains. The example adds child descriptions to a device's default child list. It retrieves switch settings that the driver previously stored in a device object's context space and then calls <b>WdfChildListAddOrUpdateChildDescriptionAsPresent</b> for each switch that is set.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDEVICE_CONTEXT  pDeviceContext;
WDFCHILDLIST  list;
UCHAR  i;
NTSTATUS  status;

pDeviceContext = GetDeviceContext(Device);
list = WdfFdoGetDefaultChildList(Device);

WdfChildListBeginScan(list);
 
for (i = 0; i &lt; RTL_BITS_OF(UCHAR); i++) {
    if (pDeviceContext-&gt;CurrentSwitchState &amp; (1&lt;&lt;i)) {
        PDO_IDENTIFICATION_DESCRIPTION description;
        WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &amp;description.Header,
                                                 sizeof(description)
                                                 );
        description.SwitchNumber = i; 
 
        status = WdfChildListAddOrUpdateChildDescriptionAsPresent(
                                                 list, 
                                                 &amp;description.Header, 
                                                 NULL
                                                 );
        if (!NT_SUCCESS(status) &amp;&amp; (status != STATUS_OBJECT_NAME_EXISTS)) {
            break;
        }
    }
}
WdfChildListEndScan(list);</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="..\wdffdo\nf-wdffdo-wdffdogetdefaultchildlist.md">WdfFdoGetDefaultChildList</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistendscan.md">WdfChildListEndScan</a>



 

 


