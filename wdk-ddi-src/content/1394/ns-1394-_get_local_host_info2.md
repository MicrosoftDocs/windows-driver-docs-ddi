---
UID: NS:1394._GET_LOCAL_HOST_INFO2
title: "_GET_LOCAL_HOST_INFO2"
description: The GET_LOCAL_HOST_INFO2 structure contains the data returned by a REQUEST_GET_LOCAL_HOST_INFO request using u.GetLocalHostInformation.nLevel GET_HOST_CAPABILITIES.
old-location: ieee\get_local_host_info2.htm
tech.root: IEEE
ms.assetid: 39cb4015-7745-4d13-bb31-76378b217cfd
ms.date: 02/15/2018
ms.keywords: "*PGET_LOCAL_HOST_INFO2, 1394/GET_LOCAL_HOST_INFO2, 1394/PGET_LOCAL_HOST_INFO2, 1394stct_06c8c818-409c-41eb-b501-6e55b0cf50ff.xml, GET_LOCAL_HOST_INFO2, GET_LOCAL_HOST_INFO2 structure [Buses], IEEE.get_local_host_info2, PGET_LOCAL_HOST_INFO2, PGET_LOCAL_HOST_INFO2 structure pointer [Buses], _GET_LOCAL_HOST_INFO2"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	1394.h
api_name:
-	GET_LOCAL_HOST_INFO2
product:
- Windows
targetos: Windows
req.typenames: GET_LOCAL_HOST_INFO2, *PGET_LOCAL_HOST_INFO2
---

# _GET_LOCAL_HOST_INFO2 structure


## -description


The GET_LOCAL_HOST_INFO2 structure contains the data returned by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a> request using <b>u.GetLocalHostInformation.nLevel</b> GET_HOST_CAPABILITIES.


## -struct-fields




### -field HostCapabilities

Indicates the host capabilities. The following table lists the values that can be assigned to th is member:



<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>HOST_INFO_PACKET_BASED </td>
<td>The host controller supports packet-based isochronous transactions. 
</td>
</tr>
<tr>
<td>HOST_INFO_STREAM_BASED </td>
<td>The host controller supports stream-based isochronous transactions.</td>
</tr>
<tr>
<td>HOST_INFO_SUPPORTS_ISOCH_STRIPPING </td>
<td>The host controller supports configurable stripping of header information. 
</td>
</tr>
<tr>
<td>HOST_INFO_SUPPORTS_START_ON_CYCLE </td>
<td>The host controller supports synchronizing start on specific isochronous cycle times. 
</td>
</tr>
<tr>
<td>HOST_INFO_SUPPORTS_RETURNING_ISO_HDR </td>
<td>The host controller does not automatically strip off the isochronous packet header. 
</td>
</tr>
<tr>
<td>HOST_INFO_SUPPORTS_ISO_HDR_INSERTION </td>
<td>The host controller supports the DESCRIPTOR_HEADER_SCATTER_GATHER flag in ISOCH_DESCRIPTOR. 
</td>
</tr>
<tr>
<td>HOST_INFO_SUPPORTS_ISO_DUAL_BUFFER_RX </td>
<td>The host controller supports the RESOURCE_VARIABLE_ISOCH_PAYLOAD flag in ISOCH_DESCRIPTOR. 
</td>
</tr>
<tr>
<td>HOST_INFO_DMA_DOUBLE_BUFFERING_ENABLED DMA </td>
<td>transfers that are made to/from the host controller will be double-buffered by using system map registers. System map registers limit the size of a single transfer. Check the MaxDmaBufferSize value that is returned in the GET_LOCAL_HOST_INFO7 structure by a REQUEST_GET_LOCAL_HOST_INFO request and limit the transfer size accordingly.</td>
</tr>
</table>
 


### -field MaxAsyncReadRequest

The bus driver fills in this member with the maximum size asynchronous read request that the host controller supports.


### -field MaxAsyncWriteRequest

The bus driver fills in this member with the maximum size asynchronous write request that the host controller supports.


## -remarks



Port drivers that return the HOST_INFO_PACKET_BASED flag support the IsochAllocateResources request's RESOURCE_USE_PACKET_BASED flag. Port drivers that return the HOST_STREAM_PACKET_BASED flag support stream-based I/O. If the host controller does not support stream-based I/O, the driver must use packet-based I/O, and set the RESOURCE_USE_PACKET_BASED flag when issuing the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>.

Some host controllers automatically strip the packet header off an isochronous packet. If a host controller does not automatically strip the header, the port driver returns the HOST_INFO_SUPPORTS_ISO_HDR flag. Some host controllers allow a driver to configure the host controller to strip off a given number of quadlets; for such controllers the port driver returns the HOST_INFO_SUPPORTS_ISOCH_STRIPPING flag. The driver should check this flag before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a> with the RESOURCE_STRIP_ADDITIONAL_QUADLETS flag.

If a host controller supports synchronizing <a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff537660">REQUEST_ISOCH_TALK</a> requests to the isochronous cycle time, the port driver returns the HOST_INFO_SUPPORTS_START_ON_CYCLE. Drivers should check this flag before attempting to issue an REQUEST_ISOCH_ALLOCATE_RESOURCES request using the RESOURCE_SYNCH_ON_TIME flag, or before attaching a buffer whose <a href="https://msdn.microsoft.com/library/windows/hardware/ff537401">ISOCH_DESCRIPTOR</a> has the DESCRIPTOR_SYNCH_ON_TIME flag set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537157">GET_LOCAL_HOST_INFO7</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537401">ISOCH_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>
 

 

