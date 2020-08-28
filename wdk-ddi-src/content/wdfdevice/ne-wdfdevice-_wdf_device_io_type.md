---
UID: NE:wdfdevice._WDF_DEVICE_IO_TYPE
title: _WDF_DEVICE_IO_TYPE (wdfdevice.h)
description: The WDF_DEVICE_IO_TYPE enumeration is used to specify a method for accessing data buffers.
old-location: wdf\wdf_device_io_type.htm
tech.root: wdf
ms.assetid: 0ad08e4f-7a9b-4052-888e-ae01c9c105c8
ms.date: 02/26/2018
keywords: ["WDF_DEVICE_IO_TYPE enumeration"]
ms.keywords: "*PWDF_DEVICE_IO_TYPE, DFDeviceObjectGeneralRef_72f77b23-a975-4ab4-bc28-312ed9682738.xml, PWDF_DEVICE_IO_TYPE, PWDF_DEVICE_IO_TYPE enumeration pointer, WDF_DEVICE_IO_TYPE, WDF_DEVICE_IO_TYPE enumeration, WdfDeviceIoBuffered, WdfDeviceIoBufferedOrDirect, WdfDeviceIoDirect, WdfDeviceIoNeither, WdfDeviceIoUndefined, _WDF_DEVICE_IO_TYPE, kmdf.wdf_device_io_type, wdf.wdf_device_io_type, wdfdevice/PWDF_DEVICE_IO_TYPE, wdfdevice/WDF_DEVICE_IO_TYPE, wdfdevice/WdfDeviceIoBuffered, wdfdevice/WdfDeviceIoBufferedOrDirect, wdfdevice/WdfDeviceIoDirect, wdfdevice/WdfDeviceIoNeither, wdfdevice/WdfDeviceIoUndefined"
req.header: wdfdevice.h
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
req.typenames: WDF_DEVICE_IO_TYPE, *PWDF_DEVICE_IO_TYPE
f1_keywords:
 - _WDF_DEVICE_IO_TYPE
 - wdfdevice/_WDF_DEVICE_IO_TYPE
 - PWDF_DEVICE_IO_TYPE
 - wdfdevice/PWDF_DEVICE_IO_TYPE
 - WDF_DEVICE_IO_TYPE
 - wdfdevice/WDF_DEVICE_IO_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfdevice.h
api_name:
 - WDF_DEVICE_IO_TYPE
---

# _WDF_DEVICE_IO_TYPE enumeration


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_IO_TYPE</b> enumeration is used to specify a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/methods-for-accessing-data-buffers">method for accessing data buffers</a>.

## -enum-fields

### -field WdfDeviceIoUndefined

Reserved for system use.

### -field WdfDeviceIoNeither

<b>UMDF </b>This value is not used by UMDF drivers. A UMDF driver can access device I/O control requests that specify the METHOD_NEITHER buffer access method by setting the <b>UmdfMethodNeitherAction</b> INF directive and using <b>WdfDeviceIoBuffered</b> or <b>WdfDeviceIoDirect</b>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

<b>KMDF </b>Neither buffered nor direct I/O will be used to access data buffers.

### -field WdfDeviceIoBuffered

Buffered I/O will be used to access data buffers.

### -field WdfDeviceIoDirect

Direct I/O will be used to access data buffers.

### -field WdfDeviceIoBufferedOrDirect

This value is not used by KMDF drivers.

<b>UMDF </b>Buffered I/O or direct I/O will be used to access data buffers.

### -field WdfDeviceIoMaximum

## -remarks

The <b>WDF_DEVICE_IO_TYPE</b> enumeration is used to specify buffer access method types in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a> structure.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a> structure is used  as input to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotype">WdfDeviceInitSetIoType</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ns-wdfdevice-_wdf_io_type_config">WDF_IO_TYPE_CONFIG</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotype">WdfDeviceInitSetIoType</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitsetiotypeex">WdfDeviceInitSetIoTypeEx</a>

