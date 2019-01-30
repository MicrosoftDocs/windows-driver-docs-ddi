---
UID: NF:wdfresource.WdfCmResourceListAppendDescriptor
title: WdfCmResourceListAppendDescriptor function (wdfresource.h)
description: The WdfCmResourceListAppendDescriptor method adds a resource descriptor to the end of a specified resource list.
old-location: wdf\wdfcmresourcelistappenddescriptor.htm
tech.root: wdf
ms.assetid: 1a0f8ea5-9b1f-4301-b96d-aa37b80b4ce2
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_13d42471-baa5-4985-a5fa-70336f2be352.xml, WdfCmResourceListAppendDescriptor, WdfCmResourceListAppendDescriptor method, kmdf.wdfcmresourcelistappenddescriptor, wdf.wdfcmresourcelistappenddescriptor, wdfresource/WdfCmResourceListAppendDescriptor
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
-	WdfCmResourceListAppendDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCmResourceListAppendDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfCmResourceListAppendDescriptor</b> method adds a resource descriptor to the end of a specified resource list.


## -parameters




### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Descriptor [in]

A pointer to a <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


## -returns



<b>WdfCmResourceListAppendDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The framework could not allocate space to store the descriptor that the <i>Descriptor</i> parameter specified.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The framework copies the contents of the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfCmResourceListAppendDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfCmResourceListAppendDescriptor</b> it can reuse the <b>CM_PARTIAL_RESOURCE_DESCRIPTOR</b> structure.

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

    status = WdfCmResourceListAppendDescriptor(
                                               Resources,
                                               &amp;newDescriptor
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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545698">WdfCmResourceListInsertDescriptor</a>
 

 

