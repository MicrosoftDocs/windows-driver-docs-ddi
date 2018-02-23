---
UID: NS:wdfiotarget._WDF_IO_TARGET_OPEN_PARAMS
title: "_WDF_IO_TARGET_OPEN_PARAMS"
author: windows-driver-content
description: The WDF_IO_TARGET_OPEN_PARAMS structure contains parameters that the WdfIoTargetOpen method uses.
old-location: wdf\wdf_io_target_open_params.htm
old-project: wdf
ms.assetid: 9539868c-127b-4781-9a73-b56fbfda3233
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: PWDF_IO_TARGET_OPEN_PARAMS, DFIOTargetRef_6363f7be-6768-4c90-88c4-88c5fdea0019.xml, WDF_IO_TARGET_OPEN_PARAMS structure, PWDF_IO_TARGET_OPEN_PARAMS structure pointer, kmdf.wdf_io_target_open_params, wdfiotarget/PWDF_IO_TARGET_OPEN_PARAMS, wdfiotarget/WDF_IO_TARGET_OPEN_PARAMS, wdf.wdf_io_target_open_params, *PWDF_IO_TARGET_OPEN_PARAMS, _WDF_IO_TARGET_OPEN_PARAMS, WDF_IO_TARGET_OPEN_PARAMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfiotarget.h
apiname:
-	WDF_IO_TARGET_OPEN_PARAMS
product: Windows
targetos: Windows
req.typenames: WDF_IO_TARGET_OPEN_PARAMS, *PWDF_IO_TARGET_OPEN_PARAMS
req.product: Windows 10 or later.
---

# _WDF_IO_TARGET_OPEN_PARAMS structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure contains parameters that the <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> method uses.


## -syntax


````
typedef struct _WDF_IO_TARGET_OPEN_PARAMS {
  ULONG                             Size;
  WDF_IO_TARGET_OPEN_TYPE           Type;
  PFN_WDF_IO_TARGET_QUERY_REMOVE    EvtIoTargetQueryRemove;
  PFN_WDF_IO_TARGET_REMOVE_CANCELED EvtIoTargetRemoveCanceled;
  PFN_WDF_IO_TARGET_REMOVE_COMPLETE EvtIoTargetRemoveComplete;
  PDEVICE_OBJECT                    TargetDeviceObject;
  PFILE_OBJECT                      TargetFileObject;
  UNICODE_STRING                    TargetDeviceName;
  ACCESS_MASK                       DesiredAccess;
  ULONG                             ShareAccess;
  ULONG                             FileAttributes;
  ULONG                             CreateDisposition;
  ULONG                             CreateOptions;
  PVOID                             EaBuffer;
  ULONG                             EaBufferLength;
  PLONGLONG                         AllocationSize;
  ULONG                             FileInformation;
  UNICODE_STRING                    FileName;
} WDF_IO_TARGET_OPEN_PARAMS, *PWDF_IO_TARGET_OPEN_PARAMS;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Type

A <a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WDF_IO_TARGET_OPEN_TYPE</a>-typed value, which indicates the type of open operation that <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> will perform.


### -field EvtIoTargetQueryRemove

A pointer to the driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a> event callback function, or <b>NULL</b>.


### -field EvtIoTargetRemoveCanceled

A pointer to the driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> event callback function, or <b>NULL</b>.


### -field EvtIoTargetRemoveComplete

A pointer to the driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_complete.md">EvtIoTargetRemoveComplete</a> event callback function, or <b>NULL</b>.


### -field TargetDeviceObject

This member is not applicable to UMDF drivers.

<b>KMDF </b>
            If the value of <b>Type</b> is <b>WdfIoTargetOpenUseExistingDevice</b>, this is a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure that represents the I/O target's device.  If the value of <b>Type</b> is not <b>WdfIoTargetOpenUseExistingDevice</b>, this member is ignored.


### -field TargetFileObject

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenUseExistingDevice</b>, this is a pointer to a <a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a> structure. This structure is included in all of the I/O requests that the driver sends to the I/O target (see <a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a>). This member is optional and can be <b>NULL</b>. 
            If the value of <b>Type</b> is not <b>WdfIoTargetOpenUseExistingDevice</b>, this member is ignored.


### -field TargetDeviceName

If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure that contains the name of a device, file, or device interface. For information about the format of this name, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557762">Object Names</a>.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.


### -field DesiredAccess

If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value. 

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.

<b>KMDF </b>Possible values include FILE_<i>Xxxx</i>_ACCESS values, such as FILE_ANY_ACCESS, FILE_SPECIAL_ACCESS, FILE_READ_ACCESS, or
    FILE_WRITE_ACCESS, as well as GENERIC_READ,
    GENERIC_WRITE, and GENERIC_ALL.

<b>UMDF </b>The most commonly used values are GENERIC_READ, GENERIC_WRITE, or both (GENERIC_READ | GENERIC_WRITE). Note that <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> is a DWORD value. For more information about this member, see the <i>dwDesiredAccess</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


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
 



<b>UMDF </b>For more information about this member, see the <i>dwShareMode</i> parameter of the <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> function in the 
    Windows SDK.

A value of zero in <b>ShareAccess</b> indicates that the driver requires exclusive access to the device.


### -field FileAttributes

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a bitwise OR of the FILE_ATTRIBUTE_<i>Xxxx</i> flags that are defined in <i>Wdm.h</i>. Most drivers specify FILE_ATTRIBUTE_NORMAL. For more information about these flags, see <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

<b>UMDF </b>For more information about 
    this member, see the <i>dwFlagsAndAttributes</i> parameter of the <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> function in the Windows SDK.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.


### -field CreateDisposition

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this value indicates an action for the system to take when opening a file. For a list of possible values, see <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

<b>UMDF </b>For more information about 
    this member, see the <i>dwCreationDisposition</i> parameter of the <a href="https://msdn.microsoft.com/80a96083-4de9-4422-9705-b8ad2b6cbd1b">CreateFile</a> function in the Windows SDK.

If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.


### -field CreateOptions

This member is not applicable to UMDF drivers.

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this is a bitwise OR of file option flags. For a list of possible flags, see <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.
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

<b>KMDF </b>If the value of <b>Type</b> is <b>WdfIoTargetOpenByName</b>, this member receives status information when the call to <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a> returns. The information is one of the following values: FILE_CREATED, FILE_OPENED, FILE_OVERWRITTEN, FILE_SUPERSEDED, FILE_EXISTS, or FILE_DOES_NOT_EXIST. If the value of <b>Type</b> is not <b>WdfIoTargetOpenByName</b>, this member is ignored.


### -field FileName

This member is not applicable to KMDF drivers.

<b>UMDF </b>A UNICODE_STRING structure that contains the 
  name of the file from which to create a file object. This member is
  optional, and is applicable only when the value of <b>Type</b> is <b>WdfIoTargetOpenLocalTargetByFile</b>.   Most drivers specify <b>NULL</b> here unless the lower target supports <a href="https://msdn.microsoft.com/e5312297-849f-4b4e-835d-0ce5295c7ce2">Device Namespace Access</a>. If supplied, the string must not contain any path separator characters 
  (forward slash or backslash).


## -remarks



Drivers should initialize the <b>WDF_IO_TARGET_OPEN_PARAMS</b> structure by calling one of the following functions:

<ul>
<li>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_existing_device.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_EXISTING_DEVICE</a>, if your driver can identify a target device by supplying a pointer to a <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a> structure. 

</li>
<li>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_create_by_name.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_CREATE_BY_NAME</a>, if the I/O target is a device, file, or device interface, and if your driver can supply the name of the device, file, or device interface. If you specify the name of a file that already exists, the system replaces the existing file. If the file does not exist, the system creates it.

</li>
<li>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_name.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_NAME</a>, if the I/O target is a device, file, or device interface, and if your driver can supply the name of the device, file, or device interface. If you specify the name of a file that already exists, the system opens the existing file. If the file does not exist, the open operation fails.

</li>
<li>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_reopen.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_REOPEN</a>, if your driver's <a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a> callback function is reopening a remote I/O target because the device was not removed.

</li>
<li>

<a href="..\wdfiotarget\nf-wdfiotarget-wdf_io_target_open_params_init_open_by_file.md">WDF_IO_TARGET_OPEN_PARAMS_INIT_OPEN_BY_FILE</a>, if your UMDF driver needs to send driver-created requests to lower targets that require an associated file object.

</li>
</ul>



## -see-also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetopen.md">WdfIoTargetOpen</a>



<a href="..\wdfrequest\nf-wdfrequest-wdfrequestgetfileobject.md">WdfRequestGetFileObject</a>



<a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>



<a href="..\wdm\ns-wdm-_file_object.md">FILE_OBJECT</a>



<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_query_remove.md">EvtIoTargetQueryRemove</a>



<a href="..\wdfiotarget\nc-wdfiotarget-evt_wdf_io_target_remove_canceled.md">EvtIoTargetRemoveCanceled</a>



<a href="..\wdfiotarget\ne-wdfiotarget-_wdf_io_target_open_type.md">WDF_IO_TARGET_OPEN_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_TARGET_OPEN_PARAMS structure%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

