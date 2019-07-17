---
UID: NF:wdfchildlist.WdfChildListUpdateChildDescriptionAsMissing
title: WdfChildListUpdateChildDescriptionAsMissing function (wdfchildlist.h)
description: The WdfChildListUpdateChildDescriptionAsMissing method informs the framework that a specified child device is currently unplugged or otherwise unavailable.
old-location: wdf\wdfchildlistupdatechilddescriptionasmissing.htm
tech.root: wdf
ms.assetid: 21932a96-285c-490d-a1fb-a137aed57bbb
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_1a871104-3d76-4ecb-936e-c27c2a107f2e.xml, WdfChildListUpdateChildDescriptionAsMissing, WdfChildListUpdateChildDescriptionAsMissing method, kmdf.wdfchildlistupdatechilddescriptionasmissing, wdf.wdfchildlistupdatechilddescriptionasmissing, wdfchildlist/WdfChildListUpdateChildDescriptionAsMissing
ms.topic: function
f1_keywords:
 - "wdfchildlist/WdfChildListUpdateChildDescriptionAsMissing"
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
- WdfChildListUpdateChildDescriptionAsMissing
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListUpdateChildDescriptionAsMissing function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListUpdateChildDescriptionAsMissing</b> method informs the framework that a specified child device is currently unplugged or otherwise unavailable.


## -parameters




### -param ChildList [in]

A handle to a child list object.


### -param IdentificationDescription [in]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies a driver-supplied child <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>.


## -returns



<b>WdfChildListUpdateChildDescriptionAsMissing</b> returns STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
The size of the structure that <i>IdentificationDescription</i> points to was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The specified device was not found in the child list.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



Your driver can report that a device is unavailable even if the driver never called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report that the device was present. In this case, the <b>WdfChildListUpdateChildDescriptionAsMissing</b> method just returns STATUS_NO_SUCH_DEVICE.

If you want to report that all devices in a child list are unavailable, your driver can simply call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>, followed immediately by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistendscan">WdfChildListEndScan</a>, instead of calling <b>WdfChildListUpdateChildDescriptionAsMissing</b> for each device.

For more information about child devices and child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that a child device with a specified serial number is unavailable.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDO_IDENTIFICATION_DESCRIPTION  description;
NTSTATUS  status;

WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                 &description.Header,
                                                 sizeof(description)
                                                 );

description.SerialNo = SerialNo;
status = WdfChildListUpdateChildDescriptionAsMissing(
                                                     list,
                                                     &description.Header
                                                     );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>
 

 

