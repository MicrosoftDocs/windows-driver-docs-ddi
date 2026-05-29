---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetDeviceObject
title: WdfIoTargetWdmGetTargetDeviceObject function (wdfiotarget.h)
description: The WdfIoTargetWdmGetTargetDeviceObject method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetdeviceobject.htm
tech.root: wdf
ms.date: 06/26/2025
keywords: ["WdfIoTargetWdmGetTargetDeviceObject function"]
ms.keywords: DFIOTargetRef_82d5005b-ced0-4ae5-8a73-8714d2895ead.xml, WdfIoTargetWdmGetTargetDeviceObject, WdfIoTargetWdmGetTargetDeviceObject method, kmdf.wdfiotargetwdmgettargetdeviceobject, wdf.wdfiotargetwdmgettargetdeviceobject, wdfiotarget/WdfIoTargetWdmGetTargetDeviceObject
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfIoTargetWdmGetTargetDeviceObject
 - wdfiotarget/WdfIoTargetWdmGetTargetDeviceObject
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
---

# WdfIoTargetWdmGetTargetDeviceObject function

## -description

\[Applies to KMDF only\]

The **WdfIoTargetWdmGetTargetDeviceObject** method returns a pointer to the Windows Driver Model (WDM) device object that is associated with a specified local or remote I/O target.

## -parameters

### -param IoTarget [in]

A handle to a local or remote I/O target object that was obtained from a previous call to **[WdfDeviceGetIoTarget](/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget)** or **[WdfIoTargetCreate](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate)** or from a method that a specialized I/O target supplies.

## -returns

**WdfIoTargetWdmGetTargetDeviceObject** returns a pointer to a WDM **[DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)** structure.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

Most framework-based drivers do not need to access an I/O target's WDM device object.

The pointer that the **WdfIoTargetWdmGetTargetDeviceObject** method returns is valid until the driver calls **[WdfIoTargetClose](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose)** or **[WdfIoTargetCloseForQueryRemove](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove)**, or until the remote I/O target object is deleted. If the driver provides an **[EvtCleanupCallback](/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup)** function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the *EvtCleanupCallback* function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The [toastmon](/samples/browse/?redirectedfrom=MSDN-samples) sample demonstrates how the driver can provide an **[EvtIoTargetQueryRemove](/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove)** callback function so that it is notified if the I/O target is removed.

For more information about **WdfIoTargetWdmGetTargetDeviceObject**, see [Obtaining Information About a General I/O Target](/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target).

For more information about I/O targets, see [Using I/O Targets](/windows-hardware/drivers/wdf/using-i-o-targets).

> [!NOTE]
> The framework does not take a reference on the target device object before returning it to the driver. The caller does not need to dereference it unless it explicitly adds a reference.

### Examples

The following code example checks an I/O target's WDM DEVICE_OBJECT structure to verify that the target supports direct I/O operations.

```cpp
if (!((WdfIoTargetWdmGetTargetDeviceObject(Adapter->IoTarget))->Flags
 & DO_DIRECT_IO)) {
    ASSERTMSG("Target device doesn't support direct I/O\n", FALSE);
    return STATUS_INVALID_DEVICE_REQUEST;
}
```

## -see-also

- **[DEVICE_OBJECT](/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object)**
- **[WdfDeviceGetIoTarget](/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetiotarget)**
- **[WdfIoTargetCreate](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate)**
- **[WdfIoTargetWdmGetTargetFileHandle](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle)**
- **[WdfIoTargetWdmGetTargetFileObject](/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfileobject)**
