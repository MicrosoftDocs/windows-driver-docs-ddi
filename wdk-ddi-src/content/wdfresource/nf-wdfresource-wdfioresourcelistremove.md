---
UID: NF:wdfresource.WdfIoResourceListRemove
title: WdfIoResourceListRemove function
author: windows-driver-content
description: The WdfIoResourceListRemove method removes a resource descriptor from a resource requirements list's logical configuration.
old-location: wdf\wdfioresourcelistremove.htm
tech.root: wdf
ms.assetid: fc67afc9-7542-4fca-bfc7-4b03b9d39735
ms.date: 2/26/2018
ms.keywords: DFResourceObjectRef_c8550890-69b9-493b-83d5-8a160eb85b8a.xml, WdfIoResourceListRemove, WdfIoResourceListRemove method, kmdf.wdfioresourcelistremove, wdf.wdfioresourcelistremove, wdfresource/WdfIoResourceListRemove
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
-	WdfIoResourceListRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoResourceListRemove function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoResourceListRemove</b> method removes a resource descriptor from a resource requirements list's <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">logical configuration</a>.


## -parameters




### -param ResourceList [in]

A handle to a framework resource-range-list object that represents a logical configuration of hardware resources for a device.


### -param Index [in]

A zero-based value that is used as an index into the logical configuration that <i>ResourceList</i> specifies.


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfIoResourceListRemove</b> method removes the resource descriptor that is associated with the index value that the <i>Index</i> parameter specifies.

When <b>WdfIoResourceListRemove</b> removes the resource descriptor that has the index value <i>n</i>, the index value of the next resource descriptor changes from <i>n</i>+1 to <i>n</i>.

For more information about resource requirements lists and logical configurations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers">Hardware Resources for Framework-Based Drivers</a>.


#### Examples

The following code example removes the first resource descriptor from a logical configuration.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfIoResourceListRemove(
                        Reslist,
                        0
                        );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548528">WdfIoResourceListRemoveByDescriptor</a>
 

 

