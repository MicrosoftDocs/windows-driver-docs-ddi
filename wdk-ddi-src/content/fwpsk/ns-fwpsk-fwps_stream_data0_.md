---
UID: NS:fwpsk.FWPS_STREAM_DATA0_
title: FWPS_STREAM_DATA0_ (fwpsk.h)
description: The FWPS_STREAM_DATA0 structure describes a portion of a data stream.Note  FWPS_STREAM_DATA0 is a specific version of FWPS_STREAM_DATA.
old-location: netvista\fwps_stream_data0.htm
tech.root: netvista
ms.assetid: 7e9daf20-12d6-42dc-99fb-9e9efe5a9900
ms.date: 05/02/2018
ms.keywords: FWPS_STREAM_DATA0, FWPS_STREAM_DATA0 structure [Network Drivers Starting with Windows Vista], FWPS_STREAM_DATA0_, fwpsk/FWPS_STREAM_DATA0, netvista.fwps_stream_data0, wfp_ref_3_struct_3_fwps_P-Z_d8d6e633-542c-4273-9341-935281133be4.xml
ms.topic: struct
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows Vista.
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
- fwpsk.h
api_name:
- FWPS_STREAM_DATA0
product:
- Windows
targetos: Windows
req.typenames: FWPS_STREAM_DATA0
---

# FWPS_STREAM_DATA0_ structure


## -description


The <b>FWPS_STREAM_DATA0</b> structure describes a portion of a data stream.
<div class="alert"><b>Note</b>  <b>FWPS_STREAM_DATA0</b> is a specific version of <b>FWPS_STREAM_DATA</b>. See <a href="https://msdn.microsoft.com/FBDF53E5-F7DE-4DEB-AC18-6D2BB59FE670">WFP Version-Independent Names and Targeting Specific Versions of Windows</a> for more information.</div><div> </div>

## -struct-fields




### -field flags

<p>A variable containing flags that specify the characteristics of the data stream.</p>

<p>For inbound data streams, this can be one or more of the following flags:</p>

#### FWPS_STREAM_FLAG_RECEIVE

Specifies that the stream is an inbound data stream. This flag is always set for inbound data
       streams.

#### FWPS_STREAM_FLAG_RECEIVE_EXPEDITED

Specifies that the inbound data stream contains high-priority out-of-band data.

#### FWPS_STREAM_FLAG_RECEIVE_DISCONNECT

Specifies that the inbound data has arrived with the FIN flag set in the TCP header. This
       indicates that the sender has disconnected the stream.

#### FWPS_STREAM_FLAG_RECEIVE_ABORT

Specifies that the inbound data has arrived with the RST flag set in the TCP header. This
       indicates that the sender has reset the stream.       

<div class="alert"><b>Note</b>  This flag is not implemented in Windows Vista.</div>

<p>For outbound data streams, this can be one or more of the following flags:</p>

#### FWPS_STREAM_FLAG_SEND

Specifies that the stream is an outbound data stream. This flag is always set for outbound data
       streams.

#### FWPS_STREAM_FLAG_SEND_EXPEDITED

Specifies that the outbound data stream contains high-priority out-of-band data.

#### FWPS_STREAM_FLAG_SEND_NODELAY

Specifies that the sending client requests that the outbound data stream is not to be buffered.
       If this flag is set, a callout driver should not hold onto the stream buffer any longer than
       necessary.

#### FWPS_STREAM_FLAG_SEND_DISCONNECT

Specifies that the stream is to be disconnected after the data in the outbound data stream has
       been sent. The network stack will set the FIN flag in the TCP header of the last packet that is sent
       out.

#### FWPS_STREAM_FLAG_SEND_ABORT

Specifies that the stream is to be reset after the data in the outbound data stream has been
       sent. The network stack will set the RST flag in the TCP header of the last packet that is sent out.
       Callout drivers must not call the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff551213">FwpsStreamInjectAsync0</a> function
       to inject data into the stream if this flag is set.       

<div class="alert"><b>Note</b>  This flag is not implemented in Windows Vista.</div>

### -field dataOffset

An 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff552420">FWPS_STREAM_DATA_OFFSET0</a> structure
     that specifies the offset into the data stream where the portion of the data stream begins.


### -field dataLength

The number of bytes in the portion of the data stream.


### -field netBufferListChain

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure that describes
     the portion of the data stream.


## -remarks



The filter engine uses the FWPS_STREAM_DATA0 structure to describe the portion of a data stream that a
    callout's 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a> callout function can process. The 
    <b>dataStream</b> member of the 
    <a href="https://msdn.microsoft.com/2c0539f0-116e-4344-9584-db7416d258e0">
    FWPS_STREAM_CALLOUT_IO_PACKET0</a> structure points to an FWPS_STREAM_DATA0 structure.




## -see-also




<a href="https://msdn.microsoft.com/2c0539f0-116e-4344-9584-db7416d258e0">
   FWPS_STREAM_CALLOUT_IO_PACKET0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552420">FWPS_STREAM_DATA_OFFSET0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551213">FwpsStreamInjectAsync0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544887">classifyFn</a>
 

 

