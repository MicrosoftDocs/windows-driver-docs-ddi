---
UID: NF:wdfobject.WdfObjectDelete
title: WdfObjectDelete function (wdfobject.h)
description: The WdfObjectDelete method deletes a framework object and its child objects.
old-location: wdf\wdfobjectdelete.htm
tech.root: wdf
ms.assetid: 09eceeb4-8501-48c4-84f5-aa747914f9dd
ms.date: 02/26/2018
ms.keywords: DFGenObjectRef_d054ae6b-e88d-46e8-ad62-2bfb23a76cd7.xml, WdfObjectDelete, WdfObjectDelete method, kmdf.wdfobjectdelete, wdf.wdfobjectdelete, wdfobject/WdfObjectDelete
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: AddPdoToStaticChildList, ControlDeviceDeleted, CtlDeviceFinishInitDeviceAdd, CtlDeviceFinishInitDrEntry, DriverCreate, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MemAfterReqCompletedIntIoctlA, MemAfterReqCompletedIoctlA, MemAfterReqCompletedReadA, MemAfterReqCompletedWriteA, ReqDelete, ReqSendFail
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: See Remarks section.
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
- WdfObjectDelete
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfObjectDelete function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfObjectDelete</b> method deletes a framework object and its child objects.


## -parameters




### -param Object [in]

A handle to framework object.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



After a driver calls <b>WdfObjectDelete</b>, the specified object is deleted after its reference count becomes zero.

Drivers cannot call <b>WdfObjectDelete</b> to delete the following framework objects, because the framework always handles deletion of these objects:

<ul>
<li>
Framework child-list objects (WDFCHILDLIST)

</li>
<li>
Framework device objects  (WDFDEVICE), unless the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a> and created a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-control-device-objects">control device object</a>, which the driver must sometimes delete

</li>
<li>
Framework driver objects (WDFDRIVER)

</li>
<li>
Framework file objects (WDFFILEOBJECT)

</li>
<li>
Framework interrupt objects (WDFINTERRUPT)

</li>
<li>
Framework queue objects (WDFQUEUE), if an object represents a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-i-o-queues">default I/O queue</a> or if the driver has called <a href="https://msdn.microsoft.com/library/windows/hardware/ff545920">WdfDeviceConfigureRequestDispatching</a> to set up the queue to receive all I/O requests of a particular type

</li>
<li>
Framework USB pipe objects (WDFUSBPIPE)

</li>
<li>
Framework USB interface objects (WDFUSBINTERFACE)

</li>
<li>
Framework WMI provider objects (WDFWMIPROVIDER)

</li>
<li>
Resource range list object
(WDFIORESLIST)

</li>
<li>
Resource list object
(WDFCMRESLIST)

</li>
<li>
Resource requirements list object
(WDFIORESREQLIST)

</li>
</ul>
See <a href="https://msdn.microsoft.com/799284a5-91c0-47b0-8f20-75a5f8e2284d">Summary of Framework Objects</a> for a complete list of framework objects.

The <b>WdfObjectDelete</b> method can return before the framework has deleted the object and its child objects. The order in which the framework deletes child objects is not predictable.

For more information about <b>WdfObjectDelete</b> and the cleanup rules for a framework object hierarchy, see <a href="https://msdn.microsoft.com/33efc3a8-ac46-4626-ba0f-beb1eaa9ee47">Framework Object Life Cycle</a>.

The <b>WdfObjectDelete</b> method must be called at IRQL &lt;= DISPATCH_LEVEL. If your driver is deleting a control device object, <b>WdfObjectDelete</b> must be called at IRQL = PASSIVE_LEVEL. Similarly, if your driver is deleting a common buffer, <b>WdfObjectDelete</b> must be called at IRQL = PASSIVE_LEVEL.

#### Examples

The following code example deletes a framework object and its child objects.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfObjectDelete(Object);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545841">WdfControlDeviceInitAllocate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548730">WdfObjectCreate</a>
 

 

