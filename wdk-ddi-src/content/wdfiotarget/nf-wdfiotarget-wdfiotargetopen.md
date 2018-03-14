---
UID: NF:wdfiotarget.WdfIoTargetOpen
title: WdfIoTargetOpen function
author: windows-driver-content
description: The WdfIoTargetOpen method opens a remote I/O target so the driver can send I/O requests to it.
old-location: wdf\wdfiotargetopen.htm
old-project: wdf
ms.assetid: 6ea2e6dd-9794-4214-8fb1-db563f49b33a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFIOTargetRef_72899f0c-58db-461c-b02c-5e99d5a0f875.xml, WdfIoTargetOpen, WdfIoTargetOpen method, kmdf.wdfiotargetopen, wdf.wdfiotargetopen, wdfiotarget/WdfIoTargetOpen
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfIoTargetOpen
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_STATE, *PWDF_IO_TARGET_STATE
req.product: Windows 10 or later.
---

# WdfIoTargetOpen function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoTargetOpen</b> method opens a remote I/O target so the driver can send I/O requests to it.


## -syntax


````
NTSTATUS WdfIoTargetOpen(
  _In_ WDFIOTARGET                IoTarget,
  _In_ PWDF_IO_TARGET_OPEN_PARAMS OpenParams
);
````


## -parameters




### -param IoTarget [in]

A handle to an I/O target object that was obtained from a previous call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>.


### -param OpenParams [in]

A pointer to a caller-allocated <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure.


## -returns



<b>WdfIoTargetOpen</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The specified I/O target is already open.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Available system resources were insufficient to complete the operation.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure that <i>OpenParams</i> specified was incorrect.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_DEVICE</b></dt>
</dl>
</td>
<td width="60%">
The <i>TargetFileObject</i> member of the caller's <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure specified an invalid file object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The device name that is identified in the <i>OpenParams</i> parameter cannot be found.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers can open remote I/O targets by supplying a Unicode string that represents an <a href="https://msdn.microsoft.com/b30e7475-7f94-4993-b373-8e4a8b1bcb4c">object name</a> or by supplying a pointer to a Windows Driver Model (WDM) <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. (Framework-based drivers typically do not have pointers to other drivers' DEVICE_OBJECT structures.)

To obtain a device interface name prior to calling <b>WdfIoTargetOpen</b>, a UMDF driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/hh780224">CM_Register_Notification</a> to register for interface arrival and removal notification. Then it can open the remote target using
the interface symbolic name that it receives in the interface notification callback routine.  The driver should continue to listen for the removal notification while the handle is open. If the target driver fails, the UMDF driver must close the handle.

 If the interface already exists, a UMDF driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff538463">CM_Get_Device_Interface_List</a>, possibly calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff538471">CM_Get_Device_Interface_List_Size</a> first to determine the required buffer size.

If you want your driver to use its local I/O target, the driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a> instead of <b>WdfIoTargetOpen</b>.

If a call to <b>WdfIoTargetOpen</b> fails, the driver should call <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a> to delete the I/O target object.

For more information about <b>WdfIoTargetOpen</b>, see <a href="https://msdn.microsoft.com/c5d5b589-09a3-4f58-83bf-2876b37b0937">Initializing a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following example creates an I/O target object, initializes a <a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a> structure, and opens a remote I/O target by specifying a device's symbolic link name.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  ioTargetAttrib;
WDFIOTARGET  ioTarget;
WDF_IO_TARGET_OPEN_PARAMS  openParams;

WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(
                                        &amp;ioTargetAttrib,
                                        TARGET_DEVICE_INFO
                                        );
status = WdfIoTargetCreate(
                           device,
                           &amp;ioTargetAttrib,
                           &amp;ioTarget
                           );
if (!NT_SUCCESS(status)) {
    return status;
}
WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME(
                                            &amp;openParams,
                                            SymbolicLink,
                                            STANDARD_RIGHTS_ALL
                                            );
status = WdfIoTargetOpen(
                         ioTarget,
                         &amp;openParams
                         );
if (!NT_SUCCESS(status)) {
    WdfObjectDelete(ioTarget);
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetiotarget.md">WdfDeviceGetIoTarget</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetcreate.md">WdfIoTargetCreate</a>



<a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetclose.md">WdfIoTargetClose</a>



<a href="..\wdfiotarget\ns-wdfiotarget-_wdf_io_target_open_params.md">WDF_IO_TARGET_OPEN_PARAMS</a>



 

 


