---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetDeviceObject
title: WdfIoTargetWdmGetTargetDeviceObject function (wdfiotarget.h)
description: The WdfIoTargetWdmGetTargetDeviceObject method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetdeviceobject.htm
tech.root: wdf
ms.assetid: 199c2fd6-ecff-4b72-b55d-086687989485
ms.date: 02/26/2018
keywords: ["WdfIoTargetWdmGetTargetDeviceObject function"]
ms.keywords: DFIOTargetRef_82d5005b-ced0-4ae5-8a73-8714d2895ead.xml, WdfIoTargetWdmGetTargetDeviceObject, WdfIoTargetWdmGetTargetDeviceObject method, kmdf.wdfiotargetwdmgettargetdeviceobject, wdf.wdfiotargetwdmgettargetdeviceobject, wdfiotarget/WdfIoTargetWdmGetTargetDeviceObject
f1_keywords:
 - "wdfiotarget/WdfIoTargetWdmGetTargetDeviceObject"
req.header: wdfiotarget.h
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfIoTargetWdmGetTargetDeviceObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetWdmGetTargetDeviceObject function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetWdmGetTargetDeviceObject</b> method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a> or from a method that a specialized I/O target supplies.


## -returns



<b>WdfIoTargetWdmGetTargetDeviceObject</b> returns a pointer to a WDM <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Most framework-based drivers do not need to access an I/O target's WDM device object.

The pointer that the <b>WdfIoTargetWdmGetTargetDeviceObject</b> method returns is valid until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="https://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetDeviceObject</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example checks an I/O target's WDM DEVICE_OBJECT structure to verify that the target supports direct I/O operations.

```cpp
if (!((WdfIoTargetWdmGetTargetDeviceObject(Adapter->IoTarget))->Flags
 & DO_DIRECT_IO)) {
    ASSERTMSG("Target device doesn't support direct I/O\n", FALSE);
    return STATUS_INVALID_DEVICE_REQUEST;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget">WdfDeviceGetIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle">WdfIoTargetWdmGetTargetFileHandle</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfileobject">WdfIoTargetWdmGetTargetFileObject</a>
 

 

