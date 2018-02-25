---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetFileHandle
title: WdfIoTargetWdmGetTargetFileHandle function
author: windows-driver-content
description: The WdfIoTargetWdmGetTargetFileHandle method returns a handle to the file that is associated with a specified remote I/O target.
old-location: wdf\wdfiotargetwdmgettargetfilehandle.htm
old-project: wdf
ms.assetid: 3312e6ca-bf2c-4a53-bd86-d36d708ed596
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , DFIOTargetRef_a3147001-4aa4-4fc2-8000-c6b1fcc4e972.xml, F, G, H, I, T, W, WdfIoTargetWdmGetTargetFileHandle, WdfIoTargetWdmGetTargetFileHandle method, a, d, e, f, g, i, kmdf.wdfiotargetwdmgettargetfilehandle, l, m, n, o, r, t, wdf.wdfiotargetwdmgettargetfilehandle, wdfiotarget/WdfIoTargetWdmGetTargetFileHandle"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfIoTargetWdmGetTargetFileHandle
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetWdmGetTargetFileHandle function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetWdmGetTargetFileHandle</b> method returns a handle to the file that is associated with a specified remote I/O target.


## -syntax


````
HANDLE WdfIoTargetWdmGetTargetFileHandle(
  _In_ WDFIOTARGET IoTarget
);
````


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


## -returns



If the driver specified an object name when it called <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>, <b>WdfIoTargetWdmGetTargetFileHandle</b> returns the file handle that is associated with the specified I/O target. Otherwise <b>WdfIoTargetWdmGetTargetFileHandle</b> returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



For KMDF, the returned file handle is a kernel-mode handle that is valid in an arbitrary thread context. For information about how a driver can use this file handle, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564923">Using a File Handle</a>. 

The file handle that the <b>WdfIoTargetWdmGetTargetFileHandle</b> method returns is valid until the driver calls <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcloseforqueryremove.md">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="..\wdfobject\nc-wdfobject-evt_wdf_object_context_cleanup.md">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="http://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For UMDF, <b>WdfIoTargetWdmGetTargetFileHandle</b> returns a Win32 HANDLE valid only in the current process.

If the driver specifies NULL for <i>FileName</i> when it calls <a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>,  <b>WdfIoTargetWdmGetTargetFileHandle</b> returns a non-NULL handle.

For more information about <b>WdfIoTargetWdmGetTargetFileHandle</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains a handle to the file that is associated with a specified remote I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HANDLE h;

h = WdfIoTargetWdmGetTargetFileHandle(IoTarget);</pre>
</td>
</tr>
</table></span></div>
A legacy UMDF driver (version 1.<i>x</i>)  calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff558841">IWDFDevice::RetrieveDeviceName</a> to get the name of the underlying kernel-mode device and then open a handle to it with <b>CreateFile</b>. The driver then sends I/O directly to the device using <b>DeviceIoControl</b>.

Starting in UMDF 2.15, the driver opens the local I/O target by file and retrieves its handle. The framework opens and closes the file handle. The file handle remains valid within the contract of <b>WdfIoTargetWdmGetTargetFileHandle</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;

WDF_IO_TARGET_OPEN_PARAMS params;

WDFIOTARGET ioTarget = NULL;

HANDLE handle = NULL;

status = WdfIoTargetCreate(Device, &amp;attr, &amp;ioTarget);

if (!NT_SUCCESS(status)) {

    // error handling

}

WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE(&amp;params, NULL);

status = WdfIoTargetOpen(ioTarget, &amp;params);

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
</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetwdmgettargetfileobject.md">WdfIoTargetWdmGetTargetFileObject</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoTargetWdmGetTargetFileHandle method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

