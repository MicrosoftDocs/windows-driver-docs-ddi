---
UID: NS:strmini._HW_STREAM_REQUEST_BLOCK
title: _HW_STREAM_REQUEST_BLOCK (strmini.h)
description: The stream class driver uses the HW_STREAM_REQUEST_BLOCK structure to pass information to and from the minidriver, using minidriver provided callbacks.
old-location: stream\hw_stream_request_block.htm
tech.root: stream
ms.assetid: e2a19bb1-631d-4160-9980-f3cbeb0b085a
ms.date: 04/23/2018
ms.keywords: "*PHW_STREAM_REQUEST_BLOCK, HW_STREAM_REQUEST_BLOCK, HW_STREAM_REQUEST_BLOCK structure [Streaming Media Devices], PHW_STREAM_REQUEST_BLOCK, PHW_STREAM_REQUEST_BLOCK structure pointer [Streaming Media Devices], _HW_STREAM_REQUEST_BLOCK, strclass-struct_4b0da124-b08a-49fe-acbc-9457db500b26.xml, stream.hw_stream_request_block, strmini/HW_STREAM_REQUEST_BLOCK, strmini/PHW_STREAM_REQUEST_BLOCK"
ms.topic: struct
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
- strmini.h
api_name:
- HW_STREAM_REQUEST_BLOCK
product:
- Windows
targetos: Windows
req.typenames: HW_STREAM_REQUEST_BLOCK, *PHW_STREAM_REQUEST_BLOCK
---

# _HW_STREAM_REQUEST_BLOCK structure


## -description


The stream class driver uses the HW_STREAM_REQUEST_BLOCK structure to pass information to and from the minidriver, using minidriver provided callbacks.


## -struct-fields




### -field SizeOfThisPacket

Specifies the size, in bytes, of this structure.


### -field Command


      Specifies the operation to be performed by the minidriver's callback. The class driver passes SRB_XXX command codes to minidriver callbacks.


### -field Status

When the minidriver completes a stream request, it fills this member with the status code of the request. See the documentation for the appropriate <b>StrMini</b><i>Xxx</i><b>Request</b> routine for the status codes minidrivers are expected to use.


### -field StreamObject

For stream oriented requests, the class driver sets this to point to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a> structure that specifies the stream the class driver is making a request on.


### -field HwDeviceExtension

Pointer to the minidriver's device extension. The minidriver may use this buffer to record private information. The minidriver sets the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>. The class driver also passes pointers to this buffer in the <b>HwDeviceExtension</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_object">HW_STREAM_OBJECT</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_time_context">HW_TIME_CONTEXT</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


### -field SRBExtension

Points to an uninitialized buffer the class driver allocates for the minidriver to use while processing this stream request block. This buffer is deallocated once the minidriver completes its handling of the block (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a> for details).


### -field CommandData

<b>CommandData</b> is a union of members provided for command-code-specific data.
      
     


### -field CommandData.DataBufferArray

Pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structures. The number of entries in this array is specified in <b>NumberOfBuffers</b>. Each KSSTREAM_HEADER describes one block of data.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-read-data">SRB_READ_DATA</a>

or <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-write-data">SRB_WRITE_DATA</a>.


### -field CommandData.StreamBuffer

Points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_stream_descriptor">HW_STREAM_DESCRIPTOR</a> structure the minidriver fills in with a description of the kernel streaming semantics it supports.


The minidriver specifies the size of this buffer in the <b>StreamDescriptorSize</b> member of its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structure.


This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-stream-info">SRB_GET_STREAM_INFO</a>.


### -field CommandData.StreamState


       The stream state.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/ksproperty-connection-state">KSPROPERTY_CONNECTION_STATE</a> for details.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-stream-state">SRB_GET_STREAM_STATE</a>

or <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-set-stream-state">SRB_SET_STREAM_STATE</a>.


### -field CommandData.TimeReference

A pointer to a STREAM_TIME_REFERENCE structure.


### -field CommandData.PropertyInfo

Points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_stream_property_descriptor">STREAM_PROPERTY_DESCRIPTOR</a> structure that specifies the parameters for the property get or set operation.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-device-property">SRB_GET_DEVICE_PROPERTY</a>,

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-set-device-property">SRB_SET_DEVICE_PROPERTY</a>,

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-stream-property">SRB_GET_STREAM_PROPERTY</a>, or

<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-set-stream-property">SRB_SET_STREAM_PROPERTY</a>.


### -field CommandData.OpenFormat

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksdataformat">KSDATAFORMAT</a> structure that specifies the format.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-open-stream">SRB_OPEN_STREAM</a>

or <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-propose-data-format">SRB_PROPOSE_DATA_FORMAT</a>.


### -field CommandData.ConfigInfo

Pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_port_configuration_information">PORT_CONFIGURATION_INFORMATION</a> structure used to initialize the device

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-initialize-device">SRB_INITIALIZE_DEVICE</a>.


### -field CommandData.MasterClockHandle

Handle for the clock object that now serves as the master clock.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-open-master-clock">SRB_OPEN_MASTER_CLOCK</a>

or <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-indicate-master-clock">SRB_INDICATE_MASTER_CLOCK</a>.


### -field CommandData.DeviceState

Specifies the new power state.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-change-power-state">SRB_CHANGE_POWER_STATE</a>.


### -field CommandData.IntersectInfo

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_stream_data_intersect_info">STREAM_DATA_INTERSECT_INFO</a> structure that describes the parameters of this operation.

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-get-data-intersection">SRB_GET_DATA_INTERSECTION</a>.


### -field CommandData.MethodInfo

Pointer to a buffer that the method data will be read from or written to.  

This member is available on Windows XP and later.


### -field CommandData.FilterTypeIndex

Filter type index for SRB_OPEN_DEVICE_INSTANCE.  

This member is available on Windows XP and later.


### -field CommandData.Idle

This member is set to <b>TRUE</b> if no open handles to the device remain.  This member is set to <b>FALSE</b>  if the device is no longer idle (a handle to the device has been opened).

This member is used when the command code is <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-notify-idle-state">SRB_NOTIFY_IDLE_STATE</a>. 

  This member is available on Windows XP and later, except for Windows Server 2003.


### -field _CommandData

<b>CommandData</b> is a union of members provided for command-code-specific data.
      
     


### -field NumberOfBuffers

If Command is either <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-read-data">SRB_READ_DATA</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/srb-write-data">SRB_WRITE_DATA</a>, then this specifies the number of entries in the array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ks/ns-ks-ksstream_header">KSSTREAM_HEADER</a> structures that begins at the address pointed to by <b>CommandData.DataBufferArray</b>. Otherwise this parameter is unused.


### -field TimeoutCounter

The number of seconds before this request times out. The class driver decrements this once per second. If the class driver decrements <b>TimeoutCounter</b> to zero before the minidriver completes this request, it will call the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_request_timeout_handler">StrMiniRequestTimeout</a> routine. If the minidriver sets this to zero, the request does not time out.


### -field TimeoutOriginal

The class driver sets this to the original value of <b>TimeoutCounter</b> upon the creation of the SRB.


### -field NextSRB

Points to another stream request block. The minidriver can use this member to queue stream request blocks.


### -field Irp

Pointer to the IRP for the request. Most minidrivers do not need to use this member.


### -field Flags

Specifies the type of request. The class driver and the minidriver can use this member to determine which callback the class driver passed this stream request block to.

<table>
<tr>
<th>Value</th>
<th>Callback used</th>
</tr>
<tr>
<td>
None

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a>


</td>
</tr>
<tr>
<td>
SRB_HW_FLAGS_STREAM_REQUEST

</td>
<td>

<a href="https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)">StrMiniReceiveStreamControlPacket</a>


</td>
</tr>
<tr>
<td>
SRB_HW_FLAGS_DATA_TRANSFER | SRB_HW_FLAGS_STREAM_REQUEST

</td>
<td>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveStreamDataPacket</a>


</td>
</tr>
</table>
 

SRB_HW_FLAGS_STREAM_REQUEST bit is set for stream-specific requests (which are passed to the minidriver's <b>StrMiniReceiveStream</b><i>Xxx</i><b>Packet</b> routines). The SRB_HW_FLAGS_DATA_TRANSFER bit is set for data transfer requests (which are passed to the minidriver's 


### -field HwInstanceExtension

Pointer to the minidriver's instance extension. The minidriver may use this buffer to record private information global to this instance of the minidriver. The minidriver sets the size of this buffer in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/ns-strmini-_hw_initialization_data">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassregisteradapter">StreamClassRegisterMinidriver</a>.


### -field NumberOfBytesToTransfer

For a SRB_READ_DATA or SRB_WRITE_DATA request, the number of bytes to be transferred.


### -field ActualBytesTransferred

For control requests, the number of bytes actually transferred. 


### -field ScatterGatherBuffer

Points to an array of KSSCATTER_GATHER structures, of the form:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef struct {
    PHYSICAL_ADDRESS PhysicalAddress;
    ULONG Length;
} KSSCATTER_GATHER, *PKSSCATTER_GATHER;</pre>
</td>
</tr>
</table></span></div>
The array describes a scatter/gather list that can be used by the minidriver to do DMA. The memory does not need to be probed, locked, mapped, or flushed -- the stream class driver performs these for the minidriver.


### -field NumberOfPhysicalPages

Specifies the size of the array passed in the <b>ScatterGatherBuffer</b> member.


### -field NumberOfScatterGatherElements

Specifies the number of physical elements pointed to by <b>ScatterGatherBuffer</b>.


### -field Reserved

 




#### - Reserved[1]

Reserved for system use. Do not use.


## -remarks



The stream class driver passes pointers to HW_STREAM_REQUEST_BLOCK structures to the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveStreamDataPacket</a>, <a href="https://docs.microsoft.com/previous-versions/ff568467(v=vs.85)">StrMiniReceiveStreamControlPacket</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_receive_device_srb">StrMiniReceiveDevicePacket</a> routines.

The minidriver owns this stream request block until the request times out or it completes the request. The minidriver signals to the class driver that it has completed the request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassdevicenotification">StreamClassDeviceNotification</a>(DeviceRequestComplete, pSrb->HwDeviceExtension, pSRB) for device-specific requests, or calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclassstreamnotification">StreamClassStreamNotification</a>(StreamRequestComplete, pSrb->StreamObject, pSrb) for stream-specific requests. (The minidriver can also complete a request by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nf-strmini-streamclasscompleterequestandmarkqueueready">StreamClassCompleteRequestAndMarkQueueReady</a>(pSrb). See that routine for details.)

If the class driver times out the request, it will call the minidriver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/strmini/nc-strmini-phw_request_timeout_handler">StrMiniRequestTimeout</a> routine, which has the responsibility of terminating processing of the request. If the minidriver queues a request for later processing, it should set the <b>TimeoutCounter</b> member to zero, which will prevent the class driver from timing out the request. Once the minidriver is ready to resume processing the request, it should reset the <b>TimeoutCounter</b> member to the value of <b>TimeoutOriginal</b>.



