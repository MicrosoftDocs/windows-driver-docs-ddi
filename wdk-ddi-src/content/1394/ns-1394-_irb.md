---
UID: NS:1394._IRB
title: _IRB (1394.h)
description: Drivers use this structure to pass most requests to IEEE 1394 bus driver.
old-location: ieee\irb.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IRB structure"]
ms.keywords: "*PIRB, 1394/IRB, 1394/PIRB, 1394stct_84bb3968-39fc-4b3b-90cb-a4e917b8310a.xml, IEEE.irb, IRB, IRB structure [Buses], PIRB, PIRB structure pointer [Buses], _IRB"
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
targetos: Windows
req.typenames: IRB, *PIRB
f1_keywords:
 - _IRB
 - 1394/_IRB
 - PIRB
 - 1394/PIRB
 - IRB
 - 1394/IRB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - _IRB
 - PIRB
 - IRB
---

# _IRB structure


## -description

Drivers use this structure to pass most requests to IEEE 1394 bus driver.

## -struct-fields

### -field FunctionNumber

Determines the type of request. Each request type is documented under the value of <b>FunctionNumber</b> in <a href="/windows-hardware/drivers/ddi/index">IEEE 1394 Bus I/O Requests</a>.

### -field Flags

Reserved. Drivers must set this member to zero with one exception. When making a <a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_ALLOCATE_BANDWIDTH</a> request, the caller can set the IRB_FLAG_ALLOW_REMOTE_FREE flag in <b>Flags</b> to indicate that the system should free the bandwidth handle memory pointed to be <b>IsochAllocateBandwidth.hBandwidth</b>. If caller does not set this flag, then caller will have to free the bandwidth handle.

### -field BusReserved

Reserved.

### -field PortReserved

Reserved.

### -field u

Specifies a union of structures, one for each value of <b>FunctionNumber</b>. The applicable submembers of <b>u</b> for each request are described with each request type in <a href="/windows-hardware/drivers/ddi/index">IEEE 1394 Bus I/O Requests</a>.

<table>
<tr>
<th>FunctionNumber</th>
<th>Associated Member</th>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ALLOCATE_ADDRESS_RANGE</a>
</td>
<td>AllocateAddressRange</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_LOCK</a>
</td>
<td>AsyncLock</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_READ</a>
</td>
<td>AsyncRead</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_STREAM</a>
</td>
<td>AsyncStream</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ASYNC_WRITE</a>
</td>
<td>AsyncWrite</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_ALLOCATE_BANDWIDTH</a>
</td>
<td>IsochAllocateBandwidth</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_DETACH_BUFFERS</a>
</td>
<td>IsochDetachBuffers</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_LISTEN</a>
</td>
<td>IsochListen</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_MODIFY_STREAM_PROPERTIES</a>
</td>
<td>IsochModifyStreamProperties</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_QUERY_RESOURCES</a>
</td>
<td>IsochQueryResources</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH</a>
</td>
<td>IsochSetChannelBandwidth</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_FREE_ADDRESS_RANGE</a>
</td>
<td>FreeAddressRange</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_CONFIG_ROM</a>
</td>
<td>GetConfigRom</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_LOCAL_HOST_INFO</a>
</td>
<td>GetLocalHostInformation</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_SPEED_BETWEEN_DEVICES</a>
</td>
<td>GetMaxSpeedBetweenDevices</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>
</td>
<td>GetSpeedTopologyMaps</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_SEND_PHY_CONFIG_PACKET</a>
</td>
<td>SendPhyConfigurationPacket</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_SEND_PHY_PACKET</a>
</td>
<td>SendPhyPacket</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_SET_LOCAL_HOST_PROPERTIES</a>
</td>
<td>SetLocalHostProperties</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">REQUEST_SET_DEVICE_XMIT_PROPERTIES</a>
</td>
<td>SetDeviceXmitProperties</td>
</tr>
<tr>
<td>
<a href="/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">REQUEST_RECEIVE_PHY_PACKET</a>
</td>
<td>ReceivePhyPackets</td>
</tr>
</table>

### -field u.AsyncRead

### -field u.AsyncWrite

### -field u.AsyncLock

### -field u.IsochAllocateBandwidth

### -field u.IsochAllocateChannel

### -field u.IsochAllocateResources

### -field u.IsochAttachBuffers

### -field u.IsochDetachBuffers

### -field u.IsochFreeBandwidth

### -field u.IsochFreeChannel

### -field u.IsochFreeResources

### -field u.IsochListen

### -field u.IsochQueryCurrentCycleTime

### -field u.IsochQueryResources

### -field u.IsochSetChannelBandwidth

### -field u.IsochStop

### -field u.IsochTalk

### -field u.IsochModifyStreamProperties

### -field u.AllocateAddressRange

### -field u.FreeAddressRange

### -field u.GetLocalHostInformation

### -field u.Get1394AddressFromDeviceObject

### -field u.Control

### -field u.GetMaxSpeedBetweenDevices

### -field u.SetDeviceXmitProperties

### -field u.SetLocalHostProperties

### -field u.GetConfigurationInformation

### -field u.GetConfigRom

### -field u.BusReset

### -field u.GetGenerationCount

### -field u.SendPhyConfigurationPacket

### -field u.SendPhyPacket

### -field u.ReceivePhyPackets

### -field u.GetSpeedTopologyMaps

### -field u.BusResetNotification

### -field u.AsyncStream

## -remarks

The <b>Parameters->Others.Arguments1</b> member of an <a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">IOCTL_1394_CLASS</a> IRP points to an IRB structure. The bus driver uses the IRB to determine the type of request made by the device driver, and also to return the results of the operation. See <a href="/windows-hardware/drivers/ddi/index">IEEE 1394 Bus I/O Requests</a> for a description of the behavior of each request.

## -see-also

<a href="/windows-hardware/drivers/ddi/1394/ni-1394-ioctl_1394_class">IOCTL_1394_CLASS</a>

