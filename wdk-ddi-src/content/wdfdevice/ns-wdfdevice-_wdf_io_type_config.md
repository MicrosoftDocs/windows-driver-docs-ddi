---
UID: NS:wdfdevice._WDF_IO_TYPE_CONFIG
title: _WDF_IO_TYPE_CONFIG (wdfdevice.h)
description: The WDF_IO_TYPE_CONFIG structure specifies the driver's preferred buffer access method for read and write requests, and for device I/O control requests.
old-location: wdf\wdf_io_type_config.htm
tech.root: wdf
ms.assetid: EB3CEC0E-5635-410D-B8D2-031FDB0557C1
ms.date: 02/26/2018
ms.keywords: "*PWDF_IO_TYPE_CONFIG, PWDF_IO_TYPE_CONFIG, PWDF_IO_TYPE_CONFIG structure pointer, WDF_IO_TYPE_CONFIG, WDF_IO_TYPE_CONFIG structure, _WDF_IO_TYPE_CONFIG, wdf.wdf_io_type_config, wdfdevice/PWDF_IO_TYPE_CONFIG, wdfdevice/WDF_IO_TYPE_CONFIG"
ms.topic: struct
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.13
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_IO_TYPE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_IO_TYPE_CONFIG, *PWDF_IO_TYPE_CONFIG
---

# _WDF_IO_TYPE_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_IO_TYPE_CONFIG</b> structure specifies the driver's preferred buffer access method for read and write requests, and for device I/O control requests.


## -struct-fields




### -field Size

Size of this structure in bytes.


### -field ReadWriteIoType

<b>KMDF </b>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that the driver will use to access data buffers 
    that it receives for read and write requests.


<b>UMDF </b>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that you prefer the driver use to access data buffers of read and write requests. Valid values include <b>WdfDeviceIoBuffered</b>           and <b>WdfDeviceIoDirect</b>.


### -field DeviceControlIoType

This member does not apply to KMDF.

<b>UMDF </b>A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>-typed enumerator that identifies the method that you prefer the driver use for the data 
    buffers of IOCTL requests. Valid values include <b>WdfDeviceIoBuffered</b>           and <b>WdfDeviceIoDirect</b>.


### -field DirectTransferThreshold

This member does not apply to KMDF.

<b>UMDF </b>An optional value that specifies the smallest buffer size, in bytes, for which 
    the framework will use direct I/O for a device. For example, set 
    <b>DirectTransferThreshold</b> to 12288 to indicate that the framework should use buffered I/O for all buffers that are smaller than 12 kilobytes, and direct I/O for buffers that are equal to or larger than 12 kilobytes. Typically, you 
    do not need to provide this value because the framework uses settings  that provide
    the best performance.


## -remarks



The <b>WDF_IO_TYPE_CONFIG</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265604">WdfDeviceInitSetIoTypeEx</a> method.

To initialize a <b>WDF_IO_TYPE_CONFIG</b> structure, your driver should call <a href="https://msdn.microsoft.com/library/windows/hardware/dn265643">WDF_IO_TYPE_CONFIG_INIT</a>.

If you are writing a driver using UMDF version 2.0 or later, see <a href="https://msdn.microsoft.com/BDB78BCD-1964-431B-BE99-CABA6DF44D7A">Managing Buffer Access Methods in UMDF Drivers</a> for more information about specifying preferred buffer access methods.


If you are writing a driver using UMDF version 1.<i>x</i>, your driver calls <a href="https://msdn.microsoft.com/7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0"> IWDFDeviceInitialize2::SetIoTypePreference</a> to specify preferred buffer access methods.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551255">WDF_DEVICE_IO_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265643">WDF_IO_TYPE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265604">WdfDeviceInitSetIoTypeEx</a>
 

 

