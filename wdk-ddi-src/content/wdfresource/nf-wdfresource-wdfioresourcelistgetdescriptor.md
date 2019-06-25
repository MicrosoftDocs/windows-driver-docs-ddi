---
UID: NF:wdfresource.WdfIoResourceListGetDescriptor
title: WdfIoResourceListGetDescriptor function (wdfresource.h)
description: The WdfIoResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistgetdescriptor.htm
tech.root: wdf
ms.assetid: 1722e6f6-7509-4ae1-b394-3c69f4596e6d
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_6cb56ab5-abf5-4915-a48f-a3c91d657806.xml, WdfIoResourceListGetDescriptor, WdfIoResourceListGetDescriptor method, kmdf.wdfioresourcelistgetdescriptor, wdf.wdfioresourcelistgetdescriptor, wdfresource/WdfIoResourceListGetDescriptor
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoResourceListGetDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListGetDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListGetDescriptor</b> method returns a pointer to a resource descriptor that is contained in a resource requirements list's <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Index [in]

A zero-based value that is used as an index into the logical configuration that <i>ResourceList</i> specifies.


## -returns



<b>WdfIoResourceListGetDescriptor</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that describes the hardware resource that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver cannot modify the contents of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a> structure that <b>WdfIoResourceListGetDescriptor</b> retrieves. To modify a resource descriptor, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfresource/nf-wdfresource-wdfioresourcelistupdatedescriptor">WdfIoResourceListUpdateDescriptor</a>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfIoResourceListGetDescriptor</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfresource/nf-wdfresource-wdfioresourcerequirementslistgetioreslist">WdfIoResourceRequirementsListGetIoResList</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ns-wdm-_io_resource_descriptor">IO_RESOURCE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfresource/nf-wdfresource-wdfioresourcelistupdatedescriptor">WdfIoResourceListUpdateDescriptor</a>
 

 

