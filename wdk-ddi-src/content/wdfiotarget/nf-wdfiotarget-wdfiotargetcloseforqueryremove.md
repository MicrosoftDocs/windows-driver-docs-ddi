---
UID: NF:wdfiotarget.WdfIoTargetCloseForQueryRemove
title: WdfIoTargetCloseForQueryRemove function (wdfiotarget.h)
description: The WdfIoTargetCloseForQueryRemove method temporarily closes a specified remote I/O target because the target device might soon be removed.
old-location: wdf\wdfiotargetcloseforqueryremove.htm
tech.root: wdf
ms.assetid: 5fa93ac6-8aee-4248-b0a6-ab82bc5486bf
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_ea857ade-1dcd-4e58-b198-50186a536159.xml, WdfIoTargetCloseForQueryRemove, WdfIoTargetCloseForQueryRemove method, kmdf.wdfiotargetcloseforqueryremove, wdf.wdfiotargetcloseforqueryremove, wdfiotarget/WdfIoTargetCloseForQueryRemove
ms.topic: function
f1_keywords:
 - "wdfiotarget/WdfIoTargetCloseForQueryRemove"
req.header: wdfiotarget.h
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
- WdfIoTargetCloseForQueryRemove
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetCloseForQueryRemove function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetCloseForQueryRemove</b> method temporarily closes a specified <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets">remote I/O target</a> because the target device might soon be removed.


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers that supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function must call <b>WdfIoTargetCloseForQueryRemove</b> from within that callback function, if the driver determines that the target device can be safely removed. 

For more information about <b>WdfIoTargetCloseForQueryRemove</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example is the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function from the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample driver. The function stops a timer, ensures that a previously submitted work item has been serviced, and then calls <b>WdfIoTargetCloseForQueryRemove</b>.

```cpp
NTSTATUS
ToastMon_EvtIoTargetQueryRemove(
    WDFIOTARGET IoTarget
)
{
    PTARGET_DEVICE_INFO  targetDeviceInfo = NULL;

    //
    // Get I/O target object's context space.
    //
    targetDeviceInfo = GetTargetDeviceInfo(IoTarget);

    //
    // Stop the timer and wait for any outstanding work items
    // to finish before closing the target.
    //
    WdfTimerStop(targetDeviceInfo->TimerForPostingRequests, TRUE);
    WdfWorkItemFlush(targetDeviceInfo->WorkItemForPostingRequests);

    WdfIoTargetCloseForQueryRemove(IoTarget);

    return STATUS_SUCCESS;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>
 

 

