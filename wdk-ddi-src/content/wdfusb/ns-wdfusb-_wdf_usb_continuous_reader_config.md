---
UID: NS:wdfusb._WDF_USB_CONTINUOUS_READER_CONFIG
title: _WDF_USB_CONTINUOUS_READER_CONFIG (wdfusb.h)
description: The WDF_USB_CONTINUOUS_READER_CONFIG structure contains information that the framework uses to configure a continuous reader for a USB pipe.
old-location: wdf\wdf_usb_continuous_reader_config.htm
tech.root: wdf
ms.assetid: 9b98d5f1-6052-4c52-b3d4-031c8a0db51c
ms.date: 02/26/2018
ms.keywords: "*PWDF_USB_CONTINUOUS_READER_CONFIG, DFUsbRef_f74973fe-cb6c-470f-acd8-805ff2ea3c19.xml, PWDF_USB_CONTINUOUS_READER_CONFIG, PWDF_USB_CONTINUOUS_READER_CONFIG structure pointer, WDF_USB_CONTINUOUS_READER_CONFIG, WDF_USB_CONTINUOUS_READER_CONFIG structure, _WDF_USB_CONTINUOUS_READER_CONFIG, kmdf.wdf_usb_continuous_reader_config, wdf.wdf_usb_continuous_reader_config, wdfusb/PWDF_USB_CONTINUOUS_READER_CONFIG, wdfusb/WDF_USB_CONTINUOUS_READER_CONFIG"
ms.topic: struct
req.header: wdfusb.h
req.include-header: Wdfusb.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfusb.h
api_name:
-	WDF_USB_CONTINUOUS_READER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_USB_CONTINUOUS_READER_CONFIG, *PWDF_USB_CONTINUOUS_READER_CONFIG
---

# _WDF_USB_CONTINUOUS_READER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_USB_CONTINUOUS_READER_CONFIG</b> structure contains information that the framework uses to configure a continuous reader for a USB pipe.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field TransferLength

The maximum length, in bytes, of data that can be received from the device.


### -field HeaderLength

An offset, in bytes, into the buffer that receives data from the device. The framework will store data from the device in a read buffer, beginning at the offset value. In other words, this space precedes the <b>TransferLength</b>-sized space in which the framework stores data from the device. 


### -field TrailerLength

The length, in bytes, of a trailing buffer space. This space follows the <b>TransferLength</b>-sized space in which the framework stores data from the device. 


### -field NumPendingReads

The number of read requests that the framework will queue to receive data from the I/O target. If this value is zero, the framework uses a default number of read requests. If the specified value is greater than the permitted maximum, the framework uses the permitted maximum. For more information about the <b>NumPendingReads</b> member, see the following Remarks section.


### -field BufferAttributes

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework memory object that the framework creates for each read request. This member can be <b>NULL</b>. You cannot set the <b>ParentObject</b> member of the WDF_OBJECT_ATTRIBUTES structure. 


### -field EvtUsbTargetPipeReadComplete

A pointer to the driver's <a href="https://msdn.microsoft.com/da762d78-6d73-4ab9-83a8-297c6f48855b">EvtUsbTargetPipeReadComplete</a> callback function.


### -field EvtUsbTargetPipeReadCompleteContext

An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="https://msdn.microsoft.com/da762d78-6d73-4ab9-83a8-297c6f48855b">EvtUsbTargetPipeReadComplete</a> callback function.


### -field EvtUsbTargetPipeReadersFailed

A pointer to the driver's <a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a> callback function. This pointer is optional and can be <b>NULL</b>. For more information about about this parameter, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a>.


## -remarks



The <b>WDF_USB_CONTINUOUS_READER_CONFIG</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a> method. 

To initialize a WDF_USB_CONTINUOUS_READER_CONFIG structure, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff552566">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>.

Use the following guidelines when choosing a value for the <b>NumPendingReads</b> member:

<ul>
<li>
Set <b>NumPendingReads</b> to 0 if you want your driver to use the framework's default value. 

The default value is greater than 1 and has been determined to provide reasonably good performance for many devices on many processor configurations. 

</li>
<li>
Set <b>NumPendingReads</b> to 1 if it is important that your driver receive data buffers in the exact order that the device delivers the data.

</li>
<li>
Set <b>NumPendingReads</b> to a number that meets the performance requirements for your device, based on thorough performance measurements.

First, test your device with the default value (0) for <b>NumPendingReads</b>. Your tests should include various hardware configurations, including different types and numbers of processors and different USB host controllers and USB configurations. You can then experiment with higher values, using the same tests. A driver that might require a higher value is one for a device that has a high interrupt rate, where data can be lost if interrupts are not serviced rapidly. 

</li>
</ul>
A <b>NumPendingReads</b> value that is too large can slow down a system's performance. You should use the lowest value that meets your performance requirements. Typically, values that are higher than 3 or 4 do not improve data throughput. But higher values might reduce latency, or the chance of missing data, on a high-frequency pipe.




## -see-also




<a href="https://msdn.microsoft.com/da762d78-6d73-4ab9-83a8-297c6f48855b">EvtUsbTargetPipeReadComplete</a>



<a href="https://msdn.microsoft.com/a9e21f47-1a60-419a-839e-8869f9fd4dd7">EvtUsbTargetPipeReadersFailed</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552400">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552566">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551130">WdfUsbTargetPipeConfigContinuousReader</a>
 

 

