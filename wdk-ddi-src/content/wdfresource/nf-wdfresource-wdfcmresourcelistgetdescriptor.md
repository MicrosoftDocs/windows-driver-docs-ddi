---
UID: NF:wdfresource.WdfCmResourceListGetDescriptor
title: WdfCmResourceListGetDescriptor function (wdfresource.h)
description: The WdfCmResourceListGetDescriptor method returns a pointer to a resource descriptor that is contained in a specified resource list.
old-location: wdf\wdfcmresourcelistgetdescriptor.htm
tech.root: wdf
ms.assetid: 5aa96fed-83ca-417e-876d-a734be6f27dd
ms.date: 02/26/2018
keywords: ["WdfCmResourceListGetDescriptor function"]
ms.keywords: DFResourceObjectRef_bdc580d1-2283-4549-a26b-cbe0f2a84e19.xml, WdfCmResourceListGetDescriptor, WdfCmResourceListGetDescriptor method, kmdf.wdfcmresourcelistgetdescriptor, wdf.wdfcmresourcelistgetdescriptor, wdfresource/WdfCmResourceListGetDescriptor
f1_keywords:
 - "wdfresource/WdfCmResourceListGetDescriptor"
 - "WdfCmResourceListGetDescriptor"
req.header: wdfresource.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
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
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfCmResourceListGetDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCmResourceListGetDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCmResourceListGetDescriptor</b> method returns a pointer to a resource descriptor that is contained in a specified resource list.


## -parameters




### -param List [in]

A handle to a framework resource-list object that represents a list of hardware resources for a device.


### -param Index [in]

A zero-based value that is used as an index into the logical configuration that <i>List</i> specifies.


## -returns



<b>WdfCmResourceListGetDescriptor</b> returns a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the hardware resource that the <i>Index</i> parameter identifies, if the index value is valid. Otherwise, the method returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



Your driver cannot modify the resource descriptor that <b>WdfCmResourceListGetDescriptor</b> retrieves. 

For more information about resource lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfCmResourceListGetDescriptor</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfcmresourcelistgetcount">WdfCmResourceListGetCount</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>
 

 

