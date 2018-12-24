---
UID: NF:wdfresource.WdfCmResourceListInsertDescriptor
title: WdfCmResourceListInsertDescriptor function
description: The WdfCmResourceListInsertDescriptor method inserts a resource descriptor into a specified resource list.
old-location: wdf\wdfcmresourcelistinsertdescriptor.htm
tech.root: wdf
ms.assetid: 18406f06-d60c-401e-a745-54caf1d0c21d
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_f55c637b-3d8b-4467-9668-bd723bc0206e.xml, WdfCmResourceListInsertDescriptor, WdfCmResourceListInsertDescriptor method, kmdf.wdfcmresourcelistinsertdescriptor, wdf.wdfcmresourcelistinsertdescriptor, wdfresource/WdfCmResourceListInsertDescriptor
ms.topic: function
req.header: wdfresource.h
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfCmResourceListInsertDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCmResourceListInsertDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCmResourceListInsertDescriptor</b> method inserts a resource descriptor into a specified resource list.


## -parameters




### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


### -param Index [in]

A zero-based value that is used as an index into the logical configuration that <i>List</i> specifies. To add a resource descriptor to the end of the resource list, specify WDF_INSERT_AT_END or the return value from <a href="https://msdn.microsoft.com/library/windows/hardware/ff545687">WdfCmResourceListGetCount</a>.


## -returns



<b>WdfCmResourceListInsertDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
An invalid parameter was specified.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The driver was not allowed to add descriptors to the logical configuration that the <i>List</i> parameter specified. For example, the driver could not modify the logical configuration that its <a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a> or <a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a> callback function received.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor that the <i>Descriptor</i> parameter points to.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ARRAY_BOUNDS_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The value that the <i>Index</i> parameter specified was too large.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfCmResourceListInsertDescriptor</b> method inserts the resource descriptor that <i>Descriptor</i> specifies into the resource list that <i>List</i> specifies, in front of the resource descriptor that <i>Index</i> value identifies.

To add a resource descriptor to the end of a resource list, specify WDF_INSERT_AT_END or the return value from <a href="https://msdn.microsoft.com/library/windows/hardware/ff545687">WdfCmResourceListGetCount</a> as the <i>Index</i> value. Alternatively, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545683">WdfCmResourceListAppendDescriptor</a> method.

The framework copies the contents of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfCmResourceListInsertDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfCmResourceListInsertDescriptor</b>, it can reuse the CM_PARTIAL_RESOURCE_DESCRIPTOR structure.

For more information about resource lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example adds a resource descriptor to the end of the resource list that an <a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a> callback function receives. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
PdoEvtDeviceResourcesQuery(
    IN WDFDEVICE  Device,
    IN WDFCMRESLIST  Resources
    )
{
    CM_PARTIAL_RESOURCE_DESCRIPTOR newDescriptor;
...
    newDescriptor.Type = CmResourceTypePort;
    newDescriptor.ShareDisposition = CmResourceShareDeviceExclusive;
    newDescriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
    newDescriptor.u.Port.Length = 1;
    newDescriptor.u.Port.Start = 0;

    status = WdfCmResourceListInsertDescriptor(
                                               Resources,
                                               &amp;newDescriptor,
                                               WDF_INSERT_AT_END
                                               );
...

}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/a3d4a983-8a75-44be-bd72-8673d89f9f87">EvtDevicePrepareHardware</a>



<a href="https://msdn.microsoft.com/b4c17e57-688c-4c76-892c-5c8abbf83f20">EvtDeviceReleaseHardware</a>



<a href="https://msdn.microsoft.com/3210b28b-cbaa-4ad9-9ca8-3b5f03aee41e">EvtDeviceResourcesQuery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545683">WdfCmResourceListAppendDescriptor</a>
 

 

