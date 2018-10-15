---
UID: NF:wdfresource.WdfIoResourceRequirementsListRemove
title: WdfIoResourceRequirementsListRemove function
author: windows-driver-content
description: The WdfIoResourceRequirementsListRemove method removes a logical configuration from a resource requirements list.
old-location: wdf\wdfioresourcerequirementslistremove.htm
tech.root: wdf
ms.assetid: 3668aa5a-1cb4-4ee1-91bd-bf2f3fa30622
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_7f7c29e8-231a-48ec-b4e3-01989ad994b0.xml, WdfIoResourceRequirementsListRemove, WdfIoResourceRequirementsListRemove method, kmdf.wdfioresourcerequirementslistremove, wdf.wdfioresourcerequirementslistremove, wdfresource/WdfIoResourceRequirementsListRemove
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
-	WdfIoResourceRequirementsListRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceRequirementsListRemove function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceRequirementsListRemove</b> method removes a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a> from a resource requirements list.


## -parameters




### -param RequirementsList [in]

A handle to a framework resource-requirements-list object that represents a device's resource requirements list.


### -param Index [in]

A zero-based value that is used as an index into the resource requirements list that <i>RequirementsList</i> specifies. 


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



The <b>WdfIoResourceRequirementsListRemove</b> method removes the logical configuration that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfIoResourceRequirementsListRemove</b> removes the logical configuration that has the index value <i>n</i>, the index value of the next logical configuration changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example removes the second logical configuration from a resource requirements list.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Example_EvtDeviceFilterRemoveResourceRequirements(
    IN WDFDEVICE Device,
    IN WDFIORESREQLIST RequirementsList
    )
{
...
    WdfIoResourceRequirementsListRemove(
                                        RequirementsList,
                                        1
                                        );
...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548575">WdfIoResourceRequirementsListRemoveByIoResList</a>
 

 

