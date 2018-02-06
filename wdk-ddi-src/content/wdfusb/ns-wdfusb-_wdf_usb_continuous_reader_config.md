---
UID: NS:wdfusb._WDF_USB_CONTINUOUS_READER_CONFIG
title: "_WDF_USB_CONTINUOUS_READER_CONFIG"
author: windows-driver-content
description: The WDF_USB_CONTINUOUS_READER_CONFIG structure contains information that the framework uses to configure a continuous reader for a USB pipe.
old-location: wdf\wdf_usb_continuous_reader_config.htm
old-project: wdf
ms.assetid: 9b98d5f1-6052-4c52-b3d4-031c8a0db51c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_USB_CONTINUOUS_READER_CONFIG, wdfusb/WDF_USB_CONTINUOUS_READER_CONFIG, PWDF_USB_CONTINUOUS_READER_CONFIG, PWDF_USB_CONTINUOUS_READER_CONFIG structure pointer, wdfusb/PWDF_USB_CONTINUOUS_READER_CONFIG, _WDF_USB_CONTINUOUS_READER_CONFIG, WDF_USB_CONTINUOUS_READER_CONFIG structure, kmdf.wdf_usb_continuous_reader_config, DFUsbRef_f74973fe-cb6c-470f-acd8-805ff2ea3c19.xml, *PWDF_USB_CONTINUOUS_READER_CONFIG, wdf.wdf_usb_continuous_reader_config
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfusb.h
apiname:
-	WDF_USB_CONTINUOUS_READER_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_USB_CONTINUOUS_READER_CONFIG, *PWDF_USB_CONTINUOUS_READER_CONFIG
req.product: Windows 10 or later.
---

# _WDF_USB_CONTINUOUS_READER_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_USB_CONTINUOUS_READER_CONFIG</b> structure contains information that the framework uses to configure a continuous reader for a USB pipe.


## -syntax


````
typedef struct _WDF_USB_CONTINUOUS_READER_CONFIG {
  ULONG                                 Size;
  size_t                                TransferLength;
  size_t                                HeaderLength;
  size_t                                TrailerLength;
  UCHAR                                 NumPendingReads;
  PWDF_OBJECT_ATTRIBUTES                BufferAttributes;
  PFN_WDF_USB_READER_COMPLETION_ROUTINE EvtUsbTargetPipeReadComplete;
  WDFCONTEXT                            EvtUsbTargetPipeReadCompleteContext;
  PFN_WDF_USB_READERS_FAILED            EvtUsbTargetPipeReadersFailed;
} WDF_USB_CONTINUOUS_READER_CONFIG, *PWDF_USB_CONTINUOUS_READER_CONFIG;
````


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

A <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that specifies object attributes for the framework memory object that the framework creates for each read request. This member can be <b>NULL</b>. You cannot set the <b>ParentObject</b> member of the WDF_OBJECT_ATTRIBUTES structure. 


### -field EvtUsbTargetPipeReadComplete

A pointer to the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a> callback function.


### -field EvtUsbTargetPipeReadCompleteContext

An untyped pointer to driver-defined context information that the framework passes to the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a> callback function.


### -field EvtUsbTargetPipeReadersFailed

A pointer to the driver's <a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_readers_failed.md">EvtUsbTargetPipeReadersFailed</a> callback function. This pointer is optional and can be <b>NULL</b>. For more information about about this parameter, see the Remarks section of <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a>.


## -remarks


The <b>WDF_USB_CONTINUOUS_READER_CONFIG</b> structure is used as input to the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a> method. 

To initialize a WDF_USB_CONTINUOUS_READER_CONFIG structure, the driver must call <a href="..\wdfusb\nf-wdfusb-wdf_usb_continuous_reader_config_init.md">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>.

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
</ul>A <b>NumPendingReads</b> value that is too large can slow down a system's performance. You should use the lowest value that meets your performance requirements. Typically, values that are higher than 3 or 4 do not improve data throughput. But higher values might reduce latency, or the chance of missing data, on a high-frequency pipe.



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeconfigcontinuousreader.md">WdfUsbTargetPipeConfigContinuousReader</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_readers_failed.md">EvtUsbTargetPipeReadersFailed</a>

<a href="..\wdfusb\nc-wdfusb-evt_wdf_usb_reader_completion_routine.md">EvtUsbTargetPipeReadComplete</a>

<a href="..\wdfusb\nf-wdfusb-wdf_usb_continuous_reader_config_init.md">WDF_USB_CONTINUOUS_READER_CONFIG_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_USB_CONTINUOUS_READER_CONFIG structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

