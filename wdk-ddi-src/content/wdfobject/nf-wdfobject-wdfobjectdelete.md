---
UID: NF:wdfobject.WdfObjectDelete
title: WdfObjectDelete function
author: windows-driver-content
description: The WdfObjectDelete method deletes a framework object and its child objects.
old-location: wdf\wdfobjectdelete.htm
old-project: wdf
ms.assetid: 09eceeb4-8501-48c4-84f5-aa747914f9dd
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfObjectDelete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfObjectDelete
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: WDF_SYNCHRONIZATION_SCOPE
req.product: Windows 10 or later.
---

# WdfObjectDelete function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfObjectDelete</b> method deletes a framework object and its child objects.



## -syntax

````
VOID WdfObjectDelete(
  _In_ WDFOBJECT Object
);
````


## -parameters

### -param Object [in]

A handle to framework object.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
After a driver calls <b>WdfObjectDelete</b>, the specified object is deleted after its reference count becomes zero.

Drivers cannot call <b>WdfObjectDelete</b> to delete the following framework objects, because the framework always handles deletion of these objects:

Framework child-list objects (WDFCHILDLIST)

Framework device objects  (WDFDEVICE), unless the driver has called <a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a> and created a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-control-device-objects">control device object</a>, which the driver must sometimes delete

Framework driver objects (WDFDRIVER)

Framework file objects (WDFFILEOBJECT)

Framework interrupt objects (WDFINTERRUPT)

Framework queue objects (WDFQUEUE), if an object represents a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">default I/O queue</a> or if the driver has called <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md">WdfDeviceConfigureRequestDispatching</a> to set up the queue to receive all I/O requests of a particular type

Framework USB pipe objects (WDFUSBPIPE)

Framework USB interface objects (WDFUSBINTERFACE)

Framework WMI provider objects (WDFWMIPROVIDER)

Resource range list object
(WDFIORESLIST)

Resource list object
(WDFCMRESLIST)

Resource requirements list object
(WDFIORESREQLIST)

See <a href="https://msdn.microsoft.com/799284a5-91c0-47b0-8f20-75a5f8e2284d">Summary of Framework Objects</a> for a complete list of framework objects.

The <b>WdfObjectDelete</b> method can return before the framework has deleted the object and its child objects. The order in which the framework deletes child objects is not predictable.

For more information about <b>WdfObjectDelete</b>, see <a href="https://msdn.microsoft.com/33efc3a8-ac46-4626-ba0f-beb1eaa9ee47">Framework Object Life Cycle</a>.

The <b>WdfObjectDelete</b> method must be called at IRQL &lt;= DISPATCH_LEVEL. If your driver is deleting a control device object, <b>WdfObjectDelete</b> must be called at IRQL = PASSIVE_LEVEL. Similarly, if your driver is deleting a common buffer, <b>WdfObjectDelete</b> must be called at IRQL = PASSIVE_LEVEL.

The following code example deletes a framework object and its child objects.


## -see-also
<dl>
<dt>
<a href="..\wdfcontrol\nf-wdfcontrol-wdfcontroldeviceinitallocate.md">WdfControlDeviceInitAllocate</a>
</dt>
<dt>
<a href="..\wdfobject\nf-wdfobject-wdfobjectcreate.md">WdfObjectCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfObjectDelete method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

