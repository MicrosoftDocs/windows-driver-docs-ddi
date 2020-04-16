---
UID: NS:1394._ISOCH_DESCRIPTOR
title: _ISOCH_DESCRIPTOR (1394.h)
description: The ISOCH_DESCRIPTOR structure describes a buffer to be attached or detailed from a resource handle, using the REQUEST_ISOCH_ATTACH_BUFFERS and REQUEST_ISOCH_DETACH_BUFFERS requests.
old-location: ieee\isoch_descriptor.htm
tech.root: IEEE
ms.assetid: 4f508af6-942b-4d48-8874-4b6d9918f01f
ms.date: 02/15/2018
keywords: ["_ISOCH_DESCRIPTOR structure"]
ms.keywords: "*PISOCH_DESCRIPTOR, 1394/ISOCH_DESCRIPTOR, 1394/PISOCH_DESCRIPTOR, 1394stct_ceca99ed-2075-42d4-9be7-31e659e2b654.xml, IEEE.isoch_descriptor, ISOCH_DESCRIPTOR, ISOCH_DESCRIPTOR structure [Buses], PISOCH_DESCRIPTOR, PISOCH_DESCRIPTOR structure pointer [Buses], _ISOCH_DESCRIPTOR"
f1_keywords:
 - "1394/ISOCH_DESCRIPTOR"
req.header: 1394.h
req.include-header: 1394.h
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
- 1394.h
api_name:
- ISOCH_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: ISOCH_DESCRIPTOR, *PISOCH_DESCRIPTOR
---

# _ISOCH_DESCRIPTOR structure

## -description

The ISOCH_DESCRIPTOR structure describes a buffer to be attached or detailed from a resource handle, using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537650">REQUEST_ISOCH_ATTACH_BUFFERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537651">REQUEST_ISOCH_DETACH_BUFFERS</a> requests.

## -struct-fields

### -field fulFlags

Specifies various flags for this isochronous descriptor. Each attached buffer on the channel has an associated isoch descriptor.

Before using a particular buffer for an I/O operation, the host controller examines the flags in the buffer's isoch descriptor for instructions on how to handle the data. In some cases, the host controller will continue to observe the behavior specified by these flags during I/O operations with subsequent buffers. For instance, if the isoch descriptor flags indicate that the host controller should filter out packets that do not have a certain Sy value recorded in <b>ulSynch</b>, the host controller will continue this filtering operation with the data in the buffers that follow, even if the isoch descriptors associated with these buffers do not have the same flags set. 

The following table describes the flags that can be assigned to this member.

<table>
<tr>
<th>Flag</th>
<th>Isochronous Transaction</th>
<th>Description</th>
</tr>
<tr>
<td>
DESCRIPTOR_SYNCH_ON_SY 

</td>
<td>
Listen

</td>
<td>
Starting with the data in current buffer, the host controller ignores all packets not containing a particular Sy value that is embedded in the isochronous packet. The Sy value is specified in <b>ulSynch</b>. If the DESCRIPTOR_USE_SY_TAG_IN_FIRST flag is set, the host controller resumes reading all packets after encountering the first packet with the Sy value specified in <b>ulSynch</b>. If the DESCRIPTOR_USE_SY_TAG_IN_FIRST flag is not set, the host controller continues filtering, reading packets with the indicated Sy value and ignoring all others. 

</td>
</tr>
<tr>
<td>
DESCRIPTOR_SYNCH_ON_TAG
</td>
<td>
Listen
</td>
<td>
Starting with the data in current buffer, the host controller ignores all packets not containing a particular tag value that is embedded in the isochronous packet. The tag value is specified in <b>ulTag</b>. If the DESCRIPTOR_USE_SY_TAG_IN_FIRST flag is set, the host controller resumes reading all packets after encountering the first packet with the tag value specified in <b>ulTag</b>. If the DESCRIPTOR_USE_SY_TAG_IN_FIRST flag is not set, the host controller continues filtering, reading packets with the indicated tag value and ignoring all others.
</td>
</tr>
<tr>
<td>
DESCRIPTOR_SYNCH_ON_TIME
</td>
<td>
Listen, Talk
</td>
<td>
The host controller waits for a particular isochronous cycle time before continuing the operation. The cycle time is specified in the <b>CycleTime</b> member. Starting with the data in the current buffer, the host controller ignores all packets not containing a cycle time of <b>CycleTime</b>. After finding a packet with the indicated cycle time, the host controller resumes processing all packets. 
</td>
</tr>
<tr>
<td>
DESCRIPTOR_USE_SY_TAG_IN_FIRST
</td>
<td>
Listen
</td>
<td>
Filtering on the <b>Sy</b> or <b>Tag</b> members occurs only until the first matching packet is received. This flag is used in conjunction with the flags DESCRIPTOR_SYNCH_ON_SY and DESCRIPTOR_SYNCH_ON_TAG. These two flags initiate a filtering operation based on the values in <b>Sy</b> or <b>Tag</b>, unless DESCRIPTOR_USE_SY_TAG_IN_FIRST is also set, in which case these flags initiate a synchronization rather than a filtering operation. In this synchronization operation the host controller ignores all packets until discovering a packet with the right <b>Sy</b> or <b>Tag</b> value. After discovering a packet with the indicated <b>Sy</b> or <b>Tag</b> value, the host controller resumes processing all packets. 
</td>
</tr>
<tr>
<td>
DESCRIPTOR_TIME_STAMP_ON_COMPLETION
</td>
<td>
Listen, Talk
</td>
<td>
Once the host controller completes its DMA to or from this buffer, store the cycle time in the <b>CycleTime</b> member of the ISOCH_DESCRIPTOR.
</td>
</tr>
<tr>
<td>
DESCRIPTOR_PRIORITY_TIME_DELIVERY
</td>
<td>
Talk
</td>
<td>
If the local host controller is not ready for a write, do not retry the write later. (The default behavior is to retry until the host controller is ready.)
</td>
</tr>
<tr>
<td>
DESCRIPTOR_HEADER_SCATTER_GATHER
</td>
<td>
Talk
</td>
<td>
The host controller treats the data in this buffer as a sequence of headers. The host controller prepends a header from this buffer to each packet it assembles from the data in the next buffer attached.
</td>
</tr>
</table>

### -field Mdl

Specifies the MDL representing a buffer in which the data is, or will be, contained.

### -field ulLength

Specifies the length of the **Mdl**.

### -field nMaxBytesPerFrame

Specifies the maximum bytes contained in each isochronous frame. On writes, the data in the buffer is split into isochronous packets of this size.

### -field ulSynch

For IsochTalk requests, if the DESCRIPTOR_SYNCH_ON_SY flag is set, this member specifies the Sy field of the outgoing packet. For REQUEST_ISOCH_LISTEN requests, if the DESCRIPTOR_SYNCH_ON_SY flag is set, this member specifies the value the host controller will match against the Sy field in isochronous packet headers.

### -field ulTag

For IsochTalk requests, this member specifies the Tag field of the outgoing packet. For REQUEST_ISOCH_LISTEN requests, if the DESCRIPTOR_SYNCH_ON_TAG flag is set, this member specifies the value the host controller will match against the Tag field in isochronous packet headers.

### -field CycleTime

If the DESCRIPTOR_SYNCH_ON_TIME flag is set, this member specifies the isochronous cycle time to synchronize on. (The timing resolution is per isochronous cycle. The **CycleOffset** member of the cycle time is not used.) If the DESCRIPTOR_TIME_STAMP_ON_COMPLETION flag is set, the bus driver fills this member with the isochronous cycle time on completion of the operation that used this buffer.

### -field Callback

Pointer to a callback routine. If non-NULL, the bus driver calls this routine to indicate that the associated attached buffers are ready to be detached. The callback executes at IRQL DISPATCH_LEVEL. The callback is of the following type:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>void Callback(IN PVOID Context1, IN PVOID Context2);</pre>
</td>
</tr>
</table></span></div>

### -field Context1

Specifies the first parameter when the bus driver calls the routine passed in **Callback**.

### -field Context2

Specifies the second parameter when the bus driver calls the routine passed in **Callback**.

### -field status

For <a href="https://msdn.microsoft.com/library/windows/hardware/ff537650">REQUEST_ISOCH_ATTACH_BUFFERS</a> requests, this member specifies the status of the attach operation on this buffer.   If an error occurs during the processing of the **REQUEST_ISOCH_ATTACH_BUFFERS** request, the bus driver fills in the **status** member with an appropriate error code.

<div class="alert"><b>Note</b>  The <b>status</b> member must be initialized to STATUS_SUCCESS before the <b>REQUEST_ISOCH_ATTACH_BUFFERS</b> request is made.</div>

### -field DeviceReserved

Reserved.

### -field BusReserved

Reserved.

### -field PortReserved

Reserved.

## -remarks

Not all DESCRIPTOR_XXX flags are supported on all hardware. The device driver can use the REQUEST_GET_LOCAL_HOST_INFO request, with **nLevel** = GET_HOST_CAPABILITIES, to determine which DESCRIPTOR_XXX flags are supported. The bus driver returns a pointer to a GET_LOCAL_HOST_INFO2 structure, whose **HostCapabilities** member contains flags that determine which flags the host controller supports. The following table lists which DESCRIPTOR_XXX flags require hardware support, and the corresponding **HostCapabilities** flag the driver should check.

<table>
<tr>
<th>DESCRIPTOR_XXX flags</th>
<th>HostCapabilities</th>
</tr>
<tr>
<td>
DESCRIPTOR_SYNCH_ON_TIME
</td>
<td>
HOST_INFO_SUPPORTS_START_ON_CYCLE
</td>
</tr>
<tr>
<td>
DESCRIPTOR_HEADER_SCATTER_GATHER
</td>
<td>
HOST_INFO_SUPPORTS_ISO_HDR_INSERTION
</td>
</tr>
</table>

If the driver sets the DESCRIPTOR_HEADER_SCATTER_GATHER flag, the host controller combines the data of the buffer specified in **Mdl** with the data of the next buffer attached. (Subsequent buffers are unaffected.) Each frame of the buffer is prepended to a frame of the next buffer (in the order the data in the buffer is split into frames), and sent as the data of the next isochronous packet. The number of frames of each buffer must match, or the bus driver returns STATUS_INVALID_PARAMETER for the next REQUEST_ISOCH_ATTACH_BUFFER request.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/1394/ns-1394-_get_local_host_info2">GET_LOCAL_HOST_INFO2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537650">REQUEST_ISOCH_ATTACH_BUFFERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537651">REQUEST_ISOCH_DETACH_BUFFERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537660">REQUEST_ISOCH_TALK</a>
