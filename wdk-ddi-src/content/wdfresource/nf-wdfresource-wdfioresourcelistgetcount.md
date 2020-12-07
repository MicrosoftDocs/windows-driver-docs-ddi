---
UID: NF:wdfresource.WdfIoResourceListGetCount
title: WdfIoResourceListGetCount function (wdfresource.h)
description: The WdfIoResourceListGetCount method returns the number of resource descriptors that are contained in a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistgetcount.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfIoResourceListGetCount function"]
ms.keywords: DFResourceObjectRef_19542c4c-aed9-412b-83c7-38209836a679.xml, WdfIoResourceListGetCount, WdfIoResourceListGetCount method, kmdf.wdfioresourcelistgetcount, wdf.wdfioresourcelistgetcount, wdfresource/WdfIoResourceListGetCount
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoResourceListGetCount
 - wdfresource/WdfIoResourceListGetCount
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
api_name:
 - WdfIoResourceListGetCount
---

# WdfIoResourceListGetCount function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListGetCount</b> method returns the number of resource descriptors that are contained in a resource requirements list's <a href="/windows-hardware/drivers/kernel/hardware-resources">logical configuration</a>.

## -parameters

### -param ResourceList 

[in]
A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.

## -returns

<b>WdfIoResourceListGetCount</b> returns the number of resource descriptors that are contained in the logical configuration that <i>ResourceList</i> specifies.

A system bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about resource requirements lists and logical configurations, see <a href="/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

For a code example that uses <b>WdfIoResourceListGetCount</b>, see <a href="/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcerequirementslistgetioreslist">WdfIoResourceRequirementsListGetIoResList</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfresource/nf-wdfresource-wdfioresourcerequirementslistgetioreslist">WdfIoResourceRequirementsListGetIoResList</a>
