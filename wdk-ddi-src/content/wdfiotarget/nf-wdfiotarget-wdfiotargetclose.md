---
UID: NF:wdfiotarget.WdfIoTargetClose
title: WdfIoTargetClose function (wdfiotarget.h)
description: The WdfIoTargetClose method closes a specified remote I/O target.
old-location: wdf\wdfiotargetclose.htm
tech.root: wdf
ms.assetid: 7de1ce11-a2b3-4d68-b279-4652b822297b
ms.date: 02/26/2018
keywords: ["WdfIoTargetClose function"]
ms.keywords: DFIOTargetRef_3ef7f2b7-6919-46d7-b48c-10dc135905d4.xml, WdfIoTargetClose, WdfIoTargetClose method, kmdf.wdfiotargetclose, wdf.wdfiotargetclose, wdfiotarget/WdfIoTargetClose
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
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoTargetClose
 - wdfiotarget/WdfIoTargetClose
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
 - WdfIoTargetClose
---

# WdfIoTargetClose function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetClose</b> method closes a specified remote I/O target.

## -parameters

### -param IoTarget 

[in]
A handle to an I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



After a driver has called <b>WdfIoTargetClose</b>, it can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> to reopen the remote I/O target.

Drivers that supply an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a> callback function must call <b>WdfIoTargetClose</b> from within that callback function.

Before the <b>WdfIoTargetClose</b> method returns, the framework <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/canceling-i-o-requests">cancels</a> all of the target queue's I/O requests. 

If a driver has finished using a remote I/O target and will not use the target again, and the target has no child request objects that are still pending, the driver can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a> without first calling <b>WdfIoTargetClose</b>. The call to <b>WdfObjectDelete</b> will close the remote I/O target, cancel all of the target queue's I/O requests, and delete the I/O target object. (Note that if the remote I/O target's parent object is a device object, the framework closes the target and deletes the target object when it deletes the parent object.) If the target has any child request objects that are still pending, the driver must call <b>WdfIoTargetClose</b> before it can safely call <b>WdfObjectDelete</b>.

For more information about <b>WdfIoTargetClose</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/controlling-a-general-i-o-target-s-state">Controlling a General I/O Target's State</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example is an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a> callback function that removes a specified I/O target from a driver's collection of I/O targets and then closes the I/O target.

```cpp
VOID
MyEvtIoTargetRemoveComplete(
    WDFIOTARGET IoTarget
)
{
    //
    // Get device information from the I/O target object's
    // context space.
    //
    targetDeviceInfo = GetTargetDeviceInfo(IoTarget);
    deviceExtension = targetDeviceInfo->DeviceExtension;

    //
    // Remove the target device from the collection.
    //
    WdfWaitLockAcquire(
                       deviceExtension->TargetDeviceCollectionLock,
                       NULL
                       );

    WdfCollectionRemove(
                        deviceExtension->TargetDeviceCollection,
                        IoTarget
                        );

    WdfWaitLockRelease(deviceExtension->TargetDeviceCollectionLock);

    //
    // Close the target.
    //
    WdfIoTargetClose(IoTarget);
}
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>

