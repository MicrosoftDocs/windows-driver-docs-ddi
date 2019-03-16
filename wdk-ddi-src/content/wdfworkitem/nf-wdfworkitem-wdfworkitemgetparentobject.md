---
UID: NF:wdfworkitem.WdfWorkItemGetParentObject
title: WdfWorkItemGetParentObject function (wdfworkitem.h)
description: The WdfWorkItemGetParentObject method returns the framework object that a specified work item is associated with.
old-location: wdf\wdfworkitemgetparentobject.htm
tech.root: wdf
ms.assetid: 6ebb1955-1ffc-4869-84c8-69d672ac782e
ms.date: 02/26/2018
ms.keywords: DFWorkItemObjectRef_d01f85c6-ab9e-413a-8352-49db7ae053d0.xml, WdfWorkItemGetParentObject, WdfWorkItemGetParentObject method, kmdf.wdfworkitemgetparentobject, wdf.wdfworkitemgetparentobject, wdfworkitem/WdfWorkItemGetParentObject
ms.topic: function
req.header: wdfworkitem.h
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
req.irql: "<= DISPATCH_LEVEL"
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
- WdfWorkItemGetParentObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWorkItemGetParentObject function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWorkItemGetParentObject</b> method returns the framework object that a specified work item is associated with.


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.


## -returns



<b>WdfWorkItemGetParentObject</b> returns a handle to the framework object that the driver specified as the <b>ParentObject</b> member of the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure when the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.


#### Examples

The following code example is an <a href="https://msdn.microsoft.com/2a2811de-9024-40a8-b8af-b61ca4100218">EvtWorkItem</a> callback function from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">1394</a> sample driver. The example obtains a work item's parent device object, calls a driver-defined routine to process the work item, and then deletes the work item object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
t1394_BusResetRoutineWorkItem(
    IN WDFWORKITEM  WorkItem
)
{
    WDFDEVICE  Device = WdfWorkItemGetParentObject(WorkItem);

    t1394_UpdateGenerationCount(Device);

    WdfObjectDelete(WorkItem);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551201">WdfWorkItemCreate</a>
 

 

