---
UID: NF:wdfdevice.WdfDeviceInitSetIoTypeEx
title: WdfDeviceInitSetIoTypeEx function
description: The WdfDeviceInitSetIoTypeEx method sets the method or preference for how a driver will access the data buffers that are included in read and write requests, as well as device I/O control requests, for a specified device.
old-location: wdf\wdfdeviceinitsetiotypeex.htm
tech.root: wdf
ms.assetid: 3746D618-C92C-43AB-A45A-2188D572105D
ms.date: 02/26/2018
ms.keywords: WdfDeviceInitSetIoTypeEx, WdfDeviceInitSetIoTypeEx method, wdf.wdfdeviceinitassigniotype, wdf.wdfdeviceinitsetiotypeex, wdfdevice/WdfDeviceInitSetIoTypeEx
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
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
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
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
-	WdfDeviceInitSetIoTypeEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDeviceInitSetIoTypeEx function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDeviceInitSetIoTypeEx</b> method sets the method or preference for how a driver will access the data buffers that are included in read and write requests, as well as device I/O control requests, for a specified device.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.


### -param IoTypeConfig [in]

Pointer to <a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a> structure initialized using WDF_IO_TYPE_CONFIG_INIT macro.


## -returns



This method does not return a value.




## -remarks



If you are writing a driver using KMDF version 1.11 or earlier, you must instead use <a href="https://msdn.microsoft.com/library/windows/hardware/ff546128">WdfDeviceInitSetIoType</a>.

<b>KMDF </b>A KMDF driver calls <b>WdfDeviceInitSetIoTypeEx</b> to set a buffer-access method for read and write requests. For device I/O control requests, the framework uses the buffer type that is encoded in the I/O control code (IOCTL).

<b>UMDF </b>A UMDF driver calls <b>WdfDeviceInitSetIoTypeEx</b> to register preferences for read and write requests, as well as device I/O control requests.  The values that a UMDF driver provides to <b>WdfDeviceInitSetIoTypeEx</b> are only preferences, and are not guaranteed to be used by the framework.  Your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/dn265602">WdfDeviceGetDeviceStackIoType</a> to determine the buffer access methods that UMDF has assigned to a device's read/write requests and I/O control requests. For I/O control requests, the access method that the framework uses might differ from the access method specified in the IOCTL and the access method requested by the driver.

If a driver calls <b>WdfDeviceInitSetIoTypeEx</b>, it must do so before it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>.

If the driver does not call <b>WdfDeviceInitSetIoTypeEx</b>, the framework sets the driver's buffer-access method to <b>WdfDeviceIoBuffered</b>, for the specified device.

Calling <b>WdfDeviceInitSetIoTypeEx</b> from a KMDF filter driver has no effect. For KMDF filter drivers, the framework uses the I/O type that the next-lower driver in the driver stack specifies.

A UMDF filter driver can, however, register preferences for buffer-access method by calling <b>WdfDeviceInitSetIoTypeEx</b>.

All UMDF drivers in a driver stack must use the same method for accessing a device's buffers. If UMDF determines that some drivers prefer either buffered I/O or direct I/O for a device while other drivers prefer only buffered I/O for the device, UMDF uses buffered I/O for all drivers. If one or more of a stack's drivers prefer only buffered I/O while others prefer only direct I/O, UMDF logs an event to the system event log and does not start the driver stack.

For more information about buffer-access methods, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers</a>.

This method is the UMDF 2.0 equivalent of <a href="https://msdn.microsoft.com/7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0"> IWDFDeviceInitialize2::SetIoTypePreference</a>.


#### Examples

The following code example initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a> structure, sets the driver's buffer-access preferences to direct I/O, specifies that transfers smaller than 32 KB should use buffered I/O, and calls <b>WdfDeviceInitSetIoTypeEx</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_IO_TYPE_CONFIG ioConfig;
WDF_IO_TYPE_CONFIG_INIT(&amp;ioConfig);
ioConfig.ReadWriteIoType = WdfDeviceIoDirect;
ioConfig.DeviceControlIoType = WdfDeviceIoDirect;
ioConfig.DirectTransferThreshold = 32;

WdfDeviceInitSetIoTypeEx(DeviceInit, &amp;ioConfig);
}
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/7d79f34d-42aa-4ac7-a63d-2f17ee0dfcf0"> IWDFDeviceInitialize2::SetIoTypePreference</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265642">WDF_IO_TYPE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265643">WDF_IO_TYPE_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265602">WdfDeviceGetDeviceStackIoType</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546128">WdfDeviceInitSetIoType</a>
 

 

