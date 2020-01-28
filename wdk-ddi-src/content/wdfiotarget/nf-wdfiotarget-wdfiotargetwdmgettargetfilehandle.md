---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetFileHandle
title: WdfIoTargetWdmGetTargetFileHandle function (wdfiotarget.h)
description: The WdfIoTargetWdmGetTargetFileHandle method returns a handle to the file that is associated with a specified remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetfilehandle.htm
tech.root: wdf
ms.assetid: 3312e6ca-bf2c-4a53-bd86-d36d708ed596
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_a3147001-4aa4-4fc2-8000-c6b1fcc4e972.xml, WdfIoTargetWdmGetTargetFileHandle, WdfIoTargetWdmGetTargetFileHandle method, kmdf.wdfiotargetwdmgettargetfilehandle, wdf.wdfiotargetwdmgettargetfilehandle, wdfiotarget/WdfIoTargetWdmGetTargetFileHandle
f1_keywords:
 - "wdfiotarget/WdfIoTargetWdmGetTargetFileHandle"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.15
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
- WdfIoTargetWdmGetTargetFileHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetWdmGetTargetFileHandle function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfIoTargetWdmGetTargetFileHandle</b> method returns a handle to the file that is associated with a specified remote I/O target.


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>.


## -returns



If the driver specified an object name when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>, <b>WdfIoTargetWdmGetTargetFileHandle</b> returns the file handle that is associated with the specified I/O target. Otherwise <b>WdfIoTargetWdmGetTargetFileHandle</b> returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For KMDF, the returned file handle is a kernel-mode handle that is valid in an arbitrary thread context. For information about how a driver can use this file handle, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-a-file-handle">Using a File Handle</a>. 

The file handle that the <b>WdfIoTargetWdmGetTargetFileHandle</b> method returns is valid until the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetclose">WdfIoTargetClose</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcloseforqueryremove">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="https://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For UMDF, <b>WdfIoTargetWdmGetTargetFileHandle</b> returns a Win32 HANDLE valid only in the current process. A legacy UMDF driver (version 1.<i>x</i>)  calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedevicename">IWDFDevice::RetrieveDeviceName</a> to get the name of the underlying kernel-mode device and then opens a handle to it with <b>CreateFile</b>. The driver can then send I/O directly to the lower device(s) using <b>DeviceIoControl</b>. Starting in UMDF 2.15, UMDF v2 drivers can open the local I/O target by file (WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE) and retrieve the file handle using [**WdfIoTargetWdmGetTargetFileHandle**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle). The framework opens and closes the file handle when the remote target is closed or deleted. The file handle remains valid within the contract of <b>WdfIoTargetWdmGetTargetFileHandle</b> described above.

> [!WARNING]
> If a UMDF v2 driver calls [**WdfIoTargetWdmGetTargetFileHandle**](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfilehandle) to obtain the Win32 handle from a remote target opened using WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE, do not submit overlapped/asynchronous I/O with APIs like **DeviceIoControl**. Doing so can crash the process hosting the driver. If the driver must submit overlapped I/O, it must also set the low-order bit of the **hEvent** member of the **OVERLAPPED** structure. This is because the framework internally binds the handle to an I/O completion port. A valid event handle whose low-order bit is set keeps I/O completion from being queued to the completion port.

For more information about <b>WdfIoTargetWdmGetTargetFileHandle</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-information-about-a-general-i-o-target">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets">Using I/O Targets</a>.


#### Examples

The following code example obtains a handle to the file that is associated with a specified remote I/O target.

```cpp
HANDLE h;

h = WdfIoTargetWdmGetTargetFileHandle(IoTarget);
```
A legacy UMDF driver (version 1.<i>x</i>)  calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice-retrievedevicename">IWDFDevice::RetrieveDeviceName</a> to get the name of the underlying kernel-mode device and then open a handle to it with <b>CreateFile</b>. The driver then sends I/O directly to the device using <b>DeviceIoControl</b>.

Starting in UMDF 2.15, the driver opens the local I/O target by file and retrieves its handle. The framework opens and closes the file handle. The file handle remains valid within the contract of <b>WdfIoTargetWdmGetTargetFileHandle</b>.

```cpp
NTSTATUS status;

WDF_IO_TARGET_OPEN_PARAMS params;

WDFIOTARGET ioTarget = NULL;

HANDLE handle = NULL;

status = WdfIoTargetCreate(Device, &attr, &ioTarget);

if (!NT_SUCCESS(status)) {

    // error handling

}

WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE(&params, NULL);

status = WdfIoTargetOpen(ioTarget, &params);

if (!NT_SUCCESS(status)) {

    // error handling

}

handle = WdfIoTargetWdmGetTargetFileHandle(ioTarget);

if (handle == NULL) {

    // error handling

}

if (ioTarget != NULL) {
    WdfIoTargetClose(ioTarget);
}
// You can now call DeviceIoControl(handle, ...) etc.
// NOTE: See Warning above on submitting overlapped or asynchronous I/O

```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetcreate">WdfIoTargetCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetwdmgettargetfileobject">WdfIoTargetWdmGetTargetFileObject</a>
 

 

