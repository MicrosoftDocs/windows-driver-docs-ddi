---
UID: NF:wdfworkitem.WdfWorkItemFlush
title: WdfWorkItemFlush function (wdfworkitem.h)
description: The WdfWorkItemFlush method returns after a specified work item has been serviced.
old-location: wdf\wdfworkitemflush.htm
tech.root: wdf
ms.assetid: 5868dd01-17ba-4edf-b665-c90d2b1aa2ba
ms.date: 02/26/2018
ms.keywords: DFWorkItemObjectRef_620a50e7-1995-4806-b71a-932f7fc7c35a.xml, WdfWorkItemFlush, WdfWorkItemFlush method, kmdf.wdfworkitemflush, wdf.wdfworkitemflush, wdfworkitem/WdfWorkItemFlush
ms.topic: function
f1_keywords:
 - "wdfworkitem/WdfWorkItemFlush"
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
req.irql: PASSIVE_LEVEL
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
- WdfWorkItemFlush
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfWorkItemFlush function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfWorkItemFlush</b> method returns after a specified work item has been serviced.


## -parameters




### -param WorkItem [in]

A handle to a framework work-item object that is obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nf-wdfworkitem-wdfworkitemcreate">WdfWorkItemCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



If your driver calls the <b>WdfWorkItemFlush</b> method, the method does not return until a system worker thread has removed the specified work item from the work-item queue and called the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a> callback function, and the <i>EvtWorkItem</i> callback function has subsequently returned after processing the work item.

Most drivers that use work items do not need to call <b>WdfWorkItemFlush</b>. A driver might call <b>WdfWorkItemFlush</b> if it must synchronize completion of work items with the removal of a remote I/O target. In this case, the driver can call <b>WdfWorkItemFlush</b> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function. 

> [!NOTE]
> It is legal to flush a workitem that is not enqueued and has never been enqueued.

For more information about work items, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-framework-work-items">Using Framework Work Items</a>.


#### Examples

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample driver. 

```cpp
NTSTATUS
ToastMon_EvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
    PTARGET_DEVICE_INFO  targetDeviceInfo = NULL;
    //
    // Get the I/O target object's context.
    //
    targetDeviceInfo = GetTargetDeviceInfo(IoTarget);
    //
    // Ensure that the I/O target's work item
    // has been processed before closing the target.
    //
    WdfWorkItemFlush(targetDeviceInfo->WorkItem);
    WdfIoTargetCloseForQueryRemove(IoTarget);

    return STATUS_SUCCESS;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfworkitem/nc-wdfworkitem-evt_wdf_workitem">EvtWorkItem</a>
 

 

