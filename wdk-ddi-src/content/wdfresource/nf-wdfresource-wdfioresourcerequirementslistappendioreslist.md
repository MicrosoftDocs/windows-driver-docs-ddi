---
UID: NF:wdfresource.WdfIoResourceRequirementsListAppendIoResList
title: WdfIoResourceRequirementsListAppendIoResList function
description: The WdfIoResourceRequirementsListAppendIoResList method adds a logical configuration to the end of a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistappendioreslist.htm
tech.root: wdf
ms.assetid: efb3617d-86be-4380-ad1a-0a333d248168
ms.date: 02/26/2018
ms.keywords: DFResourceObjectRef_1d064295-4660-4112-9512-9c5ff7196485.xml, WdfIoResourceRequirementsListAppendIoResList, WdfIoResourceRequirementsListAppendIoResList method, kmdf.wdfioresourcerequirementslistappendioreslist, wdf.wdfioresourcerequirementslistappendioreslist, wdfresource/WdfIoResourceRequirementsListAppendIoResList
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
-	WdfIoResourceRequirementsListAppendIoResList
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListAppendIoResList function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListAppendIoResList</b> method adds a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> to the end of a resource requirements list.


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param IoResList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


## -returns



<b>WdfIoResourceRequirementsListAppendIoResList</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

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
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The specified resource-requirements-list object does not own the specified resource-range-list object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The framework could not allocate space to store the resource-range-list object.

</td>
</tr>
</table>
 

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/bacd7e7c-9f71-4dda-98ed-a8d813360943">EvtDeviceResourceRequirementsQuery</a> callback function creates an empty logical configuration and appends it to a resource requirements list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceResourceRequirementsQuery(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{
    NTSTATUS  status;
    WDFIORESLIST  logConfig;

    status = WdfIoResourceListCreate(
                                     RequirementsList,
                                     WDF_NO_OBJECT_ATTRIBUTES,
                                     &amp;logConfig
                                     );
    if (!NT_SUCCESS(status)) {
        return status;
    }

    status = WdfIoResourceRequirementsListAppendIoResList(
                                             RequirementsList,
                                             logConfig
                                             );
    if (!NT_SUCCESS(status)) {
        return status;
    }
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548502">WdfIoResourceListCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548560">WdfIoResourceRequirementsListInsertIoResList</a>
 

 

