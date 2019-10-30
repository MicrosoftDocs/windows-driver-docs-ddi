---
UID: NF:wdfresource.WdfIoResourceListInsertDescriptor
title: WdfIoResourceListInsertDescriptor function (wdfresource.h)
description: The WdfIoResourceListInsertDescriptor method inserts a resource descriptor into a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistinsertdescriptor.htm
tech.root: wdf
ms.assetid: 604182ea-3712-4670-bab8-edc3cb2fcd06
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_6f8fc17d-c5db-47fa-854a-5536dfc11705.xml, WdfIoResourceListInsertDescriptor, WdfIoResourceListInsertDescriptor method, kmdf.wdfioresourcelistinsertdescriptor, wdf.wdfioresourcelistinsertdescriptor, wdfresource/WdfIoResourceListInsertDescriptor
ms.topic: function
f1_keywords:
 - "wdfresource/WdfIoResourceListInsertDescriptor"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoResourceListInsertDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListInsertDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListInsertDescriptor</b> method inserts a resource descriptor into a resource requirements list's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


### -param Index [in]

A zero-based value that is used as an index into the set of resource descriptors that are already in the logical configuration that <i>ResourceList</i> specifies. To add a resource descriptor to the end of the logical configuration, specify WDF_INSERT_AT_END or the return value from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistgetcount">WdfIoResourceListGetCount</a>.


## -returns



<b>WdfIoResourceListInsertDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
The driver was not allowed to add descriptors to the logical configuration.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ARRAY_BOUNDS_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The value that the <i>Index</i> parameter specifies was too large.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoResourceListInsertDescriptor</b> method inserts the resource descriptor that the <i>Descriptor</i> parameter points to into the logical configuration that the <i>ResourceList</i> parameter specifies, in front of the resource descriptor that the <i>Index</i> value identifies. 

To add a resource descriptor to the end of a logical configuration, specify WDF_INSERT_AT_END or the return value from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistgetcount">WdfIoResourceListGetCount</a> for the <i>Index</i> value. Alternatively, use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistappenddescriptor">WdfIoResourceListAppendDescriptor</a> method.

The framework copies the contents of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure into internal storage, so the driver routine that calls <b>WdfIoResourceListInsertDescriptor</b> can allocate the structure locally. After the driver calls <b>WdfIoResourceListInsertDescriptor</b>, the driver can reuse the <b>IO_RESOURCE_DESCRIPTOR</b> structure.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a resource descriptor and adds the descriptor to the end of a logical configuration.

```cpp
IO_RESOURCE_DESCRIPTOR descriptor;

RtlZeroMemory(&descriptor, sizeof(descriptor));

descriptor.Option = 0;
descriptor.Type = CmResourceTypePort;
descriptor.ShareDisposition = CmResourceShareDeviceExclusive;
descriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
descriptor.u.Port.Length = 1;
descriptor.u.Port.Alignment = 0x01;
descriptor.u.Port.MinimumAddress.QuadPart = 0;
descriptor.u.Port.MaximumAddress.QuadPart = 0xFFFF;

status = WdfIoResourceListInsertDescriptor(
                                           logConfig,
                                           &descriptor,
                                           WDF_INSERT_AT_END
                                           );
if (!NT_SUCCESS(status)) {
    return status;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcelistappenddescriptor">WdfIoResourceListAppendDescriptor</a>
 

 

