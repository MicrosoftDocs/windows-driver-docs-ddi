---
UID: NF:wdfresource.WdfIoResourceListUpdateDescriptor
title: WdfIoResourceListUpdateDescriptor function
author: windows-driver-content
description: The WdfIoResourceListUpdateDescriptor method updates a resource descriptor in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistupdatedescriptor.htm
old-project: wdf
ms.assetid: a571c054-380d-4d56-9094-d55868222b33
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_e9c68945-23e3-47f1-99b1-a0c62944669f.xml, WdfIoResourceListUpdateDescriptor, WdfIoResourceListUpdateDescriptor method, kmdf.wdfioresourcelistupdatedescriptor, wdf.wdfioresourcelistupdatedescriptor, wdfresource/WdfIoResourceListUpdateDescriptor
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	WdfIoResourceListUpdateDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListUpdateDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfIoResourceListUpdateDescriptor</b> method updates a resource descriptor in a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Descriptor [in]

A pointer to an <a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a> structure that describes a hardware resource.


### -param Index [in]

A zero-based value that is used as an index into the set of resource descriptors that are already in the logical configuration that <i>ResourceList</i> specifies.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoResourceListUpdateDescriptor</b> method locates the resource descriptor that the <i>Index</i> parameter identifies. Then the method copies the resource descriptor that the <i>Descriptor</i> parameter specifies into the descriptor that <i>Index</i> specifies.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


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
              &amp;newDescriptor,
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
                                  &amp;newDescriptor,
                                  1
                                  );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/03e3a656-c691-4aff-bcc8-4e0bc8390fd7">IO_RESOURCE_DESCRIPTOR</a>
 

 

