---
UID: NF:wdfresource.WdfIoResourceListUpdateDescriptor
title: WdfIoResourceListUpdateDescriptor function (wdfresource.h)
description: The WdfIoResourceListUpdateDescriptor method updates a resource descriptor in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistupdatedescriptor.htm
tech.root: wdf
ms.assetid: a571c054-380d-4d56-9094-d55868222b33
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_e9c68945-23e3-47f1-99b1-a0c62944669f.xml, WdfIoResourceListUpdateDescriptor, WdfIoResourceListUpdateDescriptor method, kmdf.wdfioresourcelistupdatedescriptor, wdf.wdfioresourcelistupdatedescriptor, wdfresource/WdfIoResourceListUpdateDescriptor
ms.topic: function
f1_keywords:
 - "wdfresource/WdfIoResourceListUpdateDescriptor"
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
- WdfIoResourceListUpdateDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListUpdateDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListUpdateDescriptor</b> method updates a resource descriptor in a resource requirements list's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


### -param Index [in]

A zero-based value that is used as an index into the set of resource descriptors that are already in the logical configuration that <i>ResourceList</i> specifies.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoResourceListUpdateDescriptor</b> method locates the resource descriptor that the <i>Index</i> parameter identifies. Then the method copies the resource descriptor that the <i>Descriptor</i> parameter specifies into the descriptor that <i>Index</i> specifies.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example initializes a new resource descriptor and then calls <b>WdfIoResourceListUpdateDescriptor</b> to replace the second descriptor in a logical configuration with the new descriptor.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>IO_RESOURCE_DESCRIPTOR newDescriptor;

RtlZeroMemory(
              &newDescriptor,
              sizeof(newDescriptor)
              );

newDescriptor.Option = 0;
newDescriptor.Type = CmResourceTypePort;
newDescriptor.ShareDisposition = CmResourceShareDeviceExclusive;
newDescriptor.Flags = CM_RESOURCE_PORT_IO|CM_RESOURCE_PORT_16_BIT_DECODE;
newDescriptor.u.Port.Length = 1;
newDescriptor.u.Port.Alignment = 0x01;
newDescriptor.u.Port.MinimumAddress.QuadPart = 0;
newDescriptor.u.Port.MaximumAddress.QuadPart = 0xFFFF;

WdfIoResourceListUpdateDescriptor(
                                  Reslist,
                                  &newDescriptor,
                                  1
                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>
 

 

