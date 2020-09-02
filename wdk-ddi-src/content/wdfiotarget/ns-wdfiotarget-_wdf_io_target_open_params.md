---
UID: NS:wdfiotarget._WDF_IO_TARGET_OPEN_PARAMS
title: _WDF_IO_TARGET_OPEN_PARAMS (wdfiotarget.h)
description: The WDF_IO_TARGET_OPEN_PARAMS structure contains parameters that the WdfIoTargetOpen method uses.
old-location: wdf\wdf_io_target_open_params.htm
tech.root: wdf
ms.assetid: 9539868c-127b-4781-9a73-b56fbfda3233
ms.date: 02/26/2018
keywords: ["WDF_IO_TARGET_OPEN_PARAMS structure"]
ms.keywords: "*PWDF_IO_TARGET_OPEN_PARAMS, DFIOTargetRef_6363f7be-6768-4c90-88c4-88c5fdea0019.xml, PWDF_IO_TARGET_OPEN_PARAMS, PWDF_IO_TARGET_OPEN_PARAMS structure pointer, WDF_IO_TARGET_OPEN_PARAMS, WDF_IO_TARGET_OPEN_PARAMS structure, _WDF_IO_TARGET_OPEN_PARAMS, kmdf.wdf_io_target_open_params, wdf.wdf_io_target_open_params, wdfiotarget/PWDF_IO_TARGET_OPEN_PARAMS, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS"
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: WDF_IO_TARGET_OPEN_PARAMS, *PWDF_IO_TARGET_OPEN_PARAMS
f1_keywords:
 - _WDF_IO_TARGET_OPEN_PARAMS
 - wdfiotarget/_WDF_IO_TARGET_OPEN_PARAMS
 - PWDF_IO_TARGET_OPEN_PARAMS
 - wdfiotarget/PWDF_IO_TARGET_OPEN_PARAMS
 - WDF_IO_TARGET_OPEN_PARAMS
 - wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfiotarget.h
api_name:
 - WDF_IO_TARGET_OPEN_PARAMS
---

# _WDF_IO_TARGET_OPEN_PARAMS structure


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure contains parameters that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> method uses.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field Type

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WDF_IO_TARGET_OPEN_TYPE</a>-typed value, which indicates the type of open operation that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> will perform.

### -field EvtIoTargetQueryRemove

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a> event callback function, or <b>NULL</b>.

### -field EvtIoTargetRemoveCanceled

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a> event callback function, or <b>NULL</b>.

### -field EvtIoTargetRemoveComplete

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_complete">EvtIoTargetRemoveComplete</a> event callback function, or <b>NULL</b>.

### -field TargetDeviceObject

This member is not applicable to UMDF drivers.

<b>KMDF </b>
            If the value of <b>Type</b> is <b>WdfIoTargetOpenUseExistingDevice</b>, this is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure that represents the I/O target's device.  If the value of <b>Type</b> is not <b>WdfIoTargetOpenUseExistingDevice</b>, this member is ignored.

### -field TargetFileObject

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenUseExistingDevice</b>, this is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a> structure. This structure is included in all of the I/O requests that the driver sends to the I/O target (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetfileobject">WdfRequestGetFileObject</a>). This member is optional and can be <b>NULL</b>. 
            If the value of <b>Type</b> is not <b>WdfIoTargetOpenUseExistingDevice</b>, this member is ignored.

### -field TargetDeviceName

If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a <a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the name of a device, file, or device interface. For information about the format of this name, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/object-names">Object Names</a>.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field DesiredAccess

If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value. 

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

<b>KMDF </b>Possible values include FILE_<i>Xxxx</i>_ACCESS values, such as FILE_ANY_ACCESS, FILE_SPECIAL_ACCESS, FILE_READ_ACCESS, or
    FILE_WRITE_ACCESS, as well as GENERIC_READ,
    GENERIC_WRITE, and GENERIC_ALL.

<b>UMDF </b>The most commonly used values are GENERIC_READ, GENERIC_WRITE, or both (GENERIC_READ | GENERIC_WRITE). Note that <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> is a DWORD value. For more information about this member, see the <i>dwDesiredAccess</i> parameter of <a href="https://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.

### -field ShareAccess

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a bitwise OR of the following flags (which are defined in <i>Wdm.h</i>), or zero. <table>
<tr>
<th>ShareAccess flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FILE_SHARE_READ

</td>
<td>
The driver does not require exclusive read access to the device.

</td>
</tr>
<tr>
<td>
FILE_SHARE_WRITE

</td>
<td>
The driver does not require exclusive write access to the device.

</td>
</tr>
<tr>
<td>
FILE_SHARE_DELETE

</td>
<td>
The driver does not require exclusive delete access to the device.

</td>
</tr>
</table>
 



<b>UMDF </b>For more information about this member, see the <i>dwShareMode</i> parameter of the <a href="https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea">CreateFile</a> function in the 
    Windows SDK.

A value of zero in <b>ShareAccess</b> indicates that the driver requires exclusive access to the device.

### -field FileAttributes

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a bitwise OR of the FILE_ATTRIBUTE_<i>Xxxx</i> flags that are defined in <i>Wdm.h</i>. Most drivers specify FILE_ATTRIBUTE_NORMAL. For more information about these flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.

<b>UMDF </b>For more information about 
    this member, see the <i>dwFlagsAndAttributes</i> parameter of the <a href="https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea">CreateFile</a> function in the Windows SDK.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field CreateDisposition

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this value indicates an action for the system to take when opening a file. For a list of possible values, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.

<b>UMDF </b>For more information about 
    this member, see the <i>dwCreationDisposition</i> parameter of the <a href="https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-createfilea">CreateFile</a> function in the Windows SDK.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field CreateOptions

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a bitwise OR of file option flags. For a list of possible flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.
             If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field EaBuffer

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this member points to an extended attributes buffer. Typically, drivers supply <b>NULL</b> for this value.
            If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field EaBufferLength

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is the length of the extended attributes buffer. Typically, drivers supply zero for this value. If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field AllocationSize

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this member specifies the size, in bytes, that the system should initially allocate for the file, if it is creating a new file. This value is optional and can be zero. If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field FileInformation

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this member receives status information when the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a> returns. The information is one of the following values: FILE_CREATED, FILE_OPENED, FILE_OVERWRITTEN, FILE_SUPERSEDED, FILE_EXISTS, or FILE_DOES_NOT_EXIST. If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

### -field FileName

This member is not applicable to KMDF drivers.

<b>UMDF </b>A UNICODE_STRING structure that contains the 
  name of the file from which to create a file object. This member is
  optional, and is applicable only when the value of <b>Type</b> is <b>WdfIoTargetOpenLocalTargetByFile</b>.   Most drivers specify <b>NULL</b> here unless the lower target supports <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/controlling-device-namespace-access">Device Namespace Access</a>. If supplied, the string must not contain any path separator characters 
  (forward slash or backslash).

## -remarks

Drivers should initialize the <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure by calling one of the following functions:

<ul>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_existing_device">WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</a>, if your driver can identify a target device by supplying a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> structure. 

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_create_by_name">WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</a>, if the I/O target is a device, file, or device interface, and if your driver can supply the name of the device, file, or device interface. If you specify the name of a file that already exists, the system replaces the existing file. If the file does not exist, the system creates it.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>, if the I/O target is a device, file, or device interface, and if your driver can supply the name of the device, file, or device interface. If you specify the name of a file that already exists, the system opens the existing file. If the file does not exist, the open operation fails.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_reopen">WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</a>, if your driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a> callback function is reopening a remote I/O target because the device was not removed.

</li>
<li>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>, if your UMDF driver needs to send driver-created requests to lower targets that require an associated file object.

</li>
</ul>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_query_remove">EvtIoTargetQueryRemove</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nc-wdfiotarget-evt_wdf_io_target_remove_canceled">EvtIoTargetRemoveCanceled</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object">FILE_OBJECT</a>



<a href="https://docs.microsoft.com/windows/win32/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/ne-wdfiotarget-_wdf_io_target_open_type">WDF_IO_TARGET_OPEN_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfiotarget/nf-wdfiotarget-wdfiotargetopen">WdfIoTargetOpen</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestgetfileobject">WdfRequestGetFileObject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>

