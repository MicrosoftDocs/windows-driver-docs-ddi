---
UID: NS:dispmprt._DXGK_SPB_INTERFACE
title: _DXGK_SPB_INTERFACE (dispmprt.h)
description: Contains pointers to functions in the Simple Peripheral Bus (SPB) Interface that the Windows Display Driver Model (WDDM) 1.2 and later display miniport driver can call to inspect and alter SPB resources.
old-location: display\dxgk_spb_interface.htm
tech.root: display
ms.assetid: 677619d2-86a1-492e-9964-d50624376ef4
ms.date: 05/10/2018
keywords: ["DXGK_SPB_INTERFACE structure"]
ms.keywords: "*PDXGK_SPB_INTERFACE, DXGK_SPB_INTERFACE, DXGK_SPB_INTERFACE structure [Display Devices], PDXGK_SPB_INTERFACE, PDXGK_SPB_INTERFACE structure pointer [Display Devices], _DXGK_SPB_INTERFACE, display.dxgk_spb_interface, dispmprt/DXGK_SPB_INTERFACE, dispmprt/PDXGK_SPB_INTERFACE"
f1_keywords:
 - "dispmprt/DXGK_SPB_INTERFACE"
 - "DXGK_SPB_INTERFACE"
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Dispmprt.h
api_name:
- DXGK_SPB_INTERFACE
targetos: Windows
req.typenames: DXGK_SPB_INTERFACE, *PDXGK_SPB_INTERFACE
---

# _DXGK_SPB_INTERFACE structure


## -description


Contains pointers to functions in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">Simple Peripheral Bus (SPB) Interface</a> that the Windows Display Driver Model (WDDM) 1.2 and later  display miniport driver can call to inspect and alter SPB resources.

To use these functions, first supply the <b>Size</b> and <b>Version</b> members of the  <b>DXGK_SPB_INTERFACE</b> structure. Then call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkcb_query_services">DxgkCbQueryServices</a> function with the  <i>ServicesType</i>  parameter set to a value of <b>DxgkServicesFirmwareTable</b>, and set the <i>Interface</i> parameter to the address (cast as <b>PINTERFACE</b>) of the <b>DXGK_SPB_INTERFACE</b> structure.

For more information on SPB architecture, see <a href="https://docs.microsoft.com/previous-versions/hh450903(v=vs.85)">Simple Peripheral Buses</a> and <a href="https://docs.microsoft.com/previous-versions/hh698226(v=vs.85)">SPB Peripheral Device Driver Overview</a>.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field Version

The version number of the SPB interface. Version number constants are defined in Dispmprt.h (for example, DXGK_SPB_INTERFACE_VERSION_1).


### -field Context

A pointer to a context that is provided by the display miniport driver.


### -field InterfaceReference

A pointer to an interface reference function that is implemented by the display miniport driver.


### -field InterfaceDereference

A pointer to an interface dereference function that is implemented by the display miniport driver.


### -field OpenSpbResource

Opens a Simple Peripheral Bus (SPB) resource. All input parameters are supplied by the display miniport driver.



#### DeviceHandle

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



#### SpbReourceId

The resource  ID of the SPB resource hub.



#### SpbResourceSubName

An optional pointer to the Unicode SPB resource subname.



#### DesiredAccess

Specifies an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> value that determines the requested access to the SPB resource. For more information, see the <i>DesiredAccess</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> function.



#### ShareAccess

Specifies the type of share access for the file. For more information, see the <i>ShareAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.



#### OpenOptions

Specifies the options to apply when opening the SPB resource. For more information, see the <i>CreateOptions</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.



#### SpbResource

A pointer to a buffer that is used to return the handle to the SPB resource.


### -field CloseSpbResource

Closes a Simple Peripheral Bus (SPB) resource. All input parameters are supplied by the display miniport driver.

Closing an open object handle causes that handle to become invalid. The system also decrements the handle count for the object and checks whether the object can be deleted. The system does not actually delete the object until all of the object's handles are closed and no referenced pointers remain.

The driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">CloseSpbResource</a> to close every handle that it has opened with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> as soon as the handle is no longer required.

Callers of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">CloseSpbResource</a> should not assume that this function automatically waits for all I/O to complete prior to returning.



#### DeviceHandle

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



#### SpbResource

A pointer to an SPB resource that the display miniport driver opened using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> function.


### -field ReadSpbResource

Reads data from an open Simple Peripheral Bus (SPB) resource. All input parameters are supplied by the display miniport driver.

If the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> set either of the <i>OpenOptions</i> flags <b>FILE_SYNCHRONOUS_IO_ALERT</b> or <b>FILE_SYNCHRONOUS_IO_NONALERT</b> (defined in Wdm.h), the I/O Manager maintains the current file position. If so, the caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">ReadSpbResource</a> can specify that the current file position offset be used instead of an explicit <i>ByteOffset</i> value. This specification can be made by using one of the following methods:<ul>
<li>Specify a pointer to a <a href="https://go.microsoft.com/fwlink/p/?linkid=243118">LARGE_INTEGER</a> value with the <b>HighPart</b> member set to -1 and the <b>LowPart</b> member set to the system-defined value <b>FILE_USE_FILE_POINTER_POSITION</b> (defined in Wdm.h).</li>
<li>Pass a <b>NULL</b> pointer for <i>ByteOffset</i>.</li>
</ul>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">ReadSpbResource</a> updates the current file position by adding the number of bytes read when it completes the read operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit <i>ByteOffset</i> value to <b>ReadSpbResource</b>. Doing this automatically changes the current file position to that <i>ByteOffset</i> value, performs the read operation, and then updates the position according to the number of bytes actually read. This technique gives the caller atomic seek-and-read service.



#### DeviceHandle

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



#### SpbResource

A pointer to an SPB resource that the display miniport driver opened using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> function.



#### Length

The size, in bytes, of the buffer pointed to by the <i>Buffer</i> parameter.



#### Buffer

A pointer to a buffer that receives the data read from the specified SPB resource.



#### ByteOffset

An optional pointer to a variable that specifies the starting byte offset in the SPB resource where the read operation will begin. If an attempt is made to read beyond the end of the file, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">ReadSpbResource</a> returns an error.

For more details on how to specify the byte offset, see the following Remarks section.



#### EventHandle

An optional handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the read operation is completed and the given event is set to the <b>Signaled</b> state.

This parameter can be <b>NULL</b>.



#### IoStatusBlock

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested read operation. The  <b>Information</b> member of the <b>IO_STATUS_BLOCK</b> structure receives the number of bytes actually read from the SPB resource.




### -field WriteSpbResource

Writes data to an open Simple Peripheral Bus (SPB) resource.

If the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> function set only the <i>DesiredAccess</i> flag <b>FILE_APPEND_DATA</b>, the <i>ByteOffset</i> parameter is ignored. In this case, data in the buffer pointed to by the <i>Buffer</i> parameter, for <b>Length</b> bytes, is written starting at the current end of file.



If the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> set either of the <i>CreateOptions</i> flags, <b>FILE_SYNCHRONOUS_IO_ALERT</b> or <b>FILE_SYNCHRONOUS_IO_NONALERT</b>, the I/O Manager maintains the current file position. If so, the caller of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">WriteSpbResource</a> can specify that the current file position offset be used instead of an explicit <i>ByteOffset</i> value. This specification can be made by using one of the following methods:<ul>
<li>Specify a pointer to a <a href="https://go.microsoft.com/fwlink/p/?linkid=243118">LARGE_INTEGER</a> value with the <b>HighPart</b> member set to -1 and the <b>LowPart</b> member set to the system-defined value <b>FILE_USE_FILE_POINTER_POSITION</b> (defined in Wdm.h).</li>
<li>Pass a <b>NULL</b> pointer for <i>ByteOffset</i>.</li>
</ul>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">WriteSpbResource</a> updates the current file position by adding the number of bytes written when it completes the write operation, if it is using the current file position maintained by the I/O Manager.

Even when the I/O Manager is maintaining the current file position, the caller can reset this position by passing an explicit <i>ByteOffset</i> value to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">WriteSpbResource</a>. Doing this automatically changes the current file position to that <i>ByteOffset</i> value, performs the write operation, and then updates the position according to the number of bytes actually written. This technique gives the caller atomic seek-and-write service.

It is also possible to cause a write operation to start at the current end of file by specifying for <i>ByteOffset</i> a pointer to a <a href="https://go.microsoft.com/fwlink/p/?linkid=243118">LARGE_INTEGER</a> value with <b>HighPart</b> set to -1 and <b>LowPart</b> set to <b>FILE_WRITE_TO_END_OF_FILE</b>. This works regardless of whether the I/O Manager is maintaining the current file position.



#### DeviceHandle

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



#### SpbResource

A pointer to an SPB resource that the display miniport driver opened using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> function.



#### Length

The size, in bytes, of the buffer pointed to by the <i>Buffer</i> parameter.



#### Buffer

A pointer to a caller-allocated buffer that contains the data to be written to the specified SPB resource.



#### ByteOffset

An optional pointer to a variable that specifies the starting byte offset in the SPB resource where the write operation will begin. If the <i>Length</i> and <i>ByteOffset</i> parameters specify a write operation past the current end-of-file mark, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">WriteSpbResource</a> automatically extends the file and updates the end-of-file mark; any bytes that are not explicitly written between such old and new end-of-file marks are defined to be zero.

For more details on how to specify the byte offset, see the following Remarks section.



#### EventHandle

An optional handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the write operation is completed and the given event is set to the <b>Signaled</b> state.

This parameter can be <b>NULL</b>.



#### IoStatusBlock

A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure that receives the final completion status and information about the requested write operation. The <b>Information</b> member of the  <b>IO_STATUS_BLOCK</b> structure receives the number of bytes actually written to the SPB resource.


### -field SpbResourceIoControl

Performs an I/O control operation on an open Simple Peripheral Bus (SPB) resource. All input parameters are supplied by the display miniport driver.

If the caller opened the file for asynchronous I/O (with neither <b>FILE_SYNCHRONOUS_XXX</b> create/open option set), the specified event, if any, will be set to the <b>Signaled</b> state when the device control operation completes. Otherwise, the file object specified by the <i>DeviceHandle</i> parameter will be set to the <b>Signaled</b> state.



#### DeviceHandle

A handle that represents a display adapter. The display miniport driver previously obtained this handle in the <b>DeviceHandle</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgkrnl_interface">DXGKRNL_INTERFACE</a> structure that was passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_start_device">DxgkDdiStartDevice</a> function.



#### SpbResource

A pointer to an SPB resource that the display miniport driver opened using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a> function.



#### IoControlCode

A device I/O control code (IOCTL_XXX) that indicates which device I/O control operation is to be carried out on, usually by the underlying device driver. The value of this parameter determines the format and required length of the <i>InputBuffer</i> and <i>OutputBuffer</i> parameters, as well as which of the following parameter pairs are required.



#### InBufferSize

The size, in bytes, of the buffer pointed to by the <i>InputBuffer</i> parameter. This value is ignored if <i>InputBuffer</i> is <b>NULL</b>.





#### InputBuffer

A pointer to a caller-allocated input buffer that contains device-specific information to be given to the target device. If the <i>IoControlCode</i> parameter specifies an operation that does not require input data, this pointer can be <b>NULL</b>.



#### OutBufferSize

The size, in bytes, of the buffer pointed to by the <i>OutputBuffer</i> parameter. This value is ignored if <i>OutputBuffer</i> is <b>NULL</b>.





#### OutputBuffer

A pointer to a caller-allocated output buffer in which information is returned from the target device. If the <i>IoControlCode</i> parameter  specifies an operation that does not produce output data, this pointer can be <b>NULL</b>



#### EventHandle

An optional handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the <b>Signaled</b> state.

This parameter can be <b>NULL</b>.



#### IoStatusBlock

A pointer to a variable that receives the final completion status and information about the requested I/O control operation. For successful calls that return data, the number of bytes written to the buffer pointed to by the <i>OutputBuffer</i> parameter is returned in the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block">IO_STATUS_BLOCK</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">CloseSpbResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">OpenSpbResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">ReadSpbResource</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">SpbResourceIoControl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dispmprt/ns-dispmprt-_dxgk_spb_interface">WriteSpbResource</a>
 

 

