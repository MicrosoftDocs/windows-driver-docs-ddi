---
UID: NS:1394._IRB
title: "_IRB"
author: windows-driver-content
description: Drivers use this structure to pass most requests to IEEE 1394 bus driver.
old-location: ieee\irb.htm
old-project: IEEE
ms.assetid: 456712c9-720c-436c-b1db-a6d53c358e22
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1394stct_84bb3968-39fc-4b3b-90cb-a4e917b8310a.xml, IRB, 1394/IRB, *PIRB, PIRB, _IRB, 1394/PIRB, PIRB structure pointer [Buses], IEEE.irb, IRB structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	1394.h
apiname:
-	IRB
product: Windows
targetos: Windows
req.typenames: "*PIRB, IRB"
---

# _IRB structure


## -description


Drivers use this structure to pass most requests to IEEE 1394 bus driver.


## -syntax


````
typedef struct _IRB {
  ULONG     FunctionNumber;
  ULONG     Flags;
  ULONG_PTR BusReserved[IRB_BUS_RESERVED_SZ];
  ULONG_PTR PortReserved[IRB_PORT_RESERVED_SZ];
  union  u;
} IRB, *PIRB;
````


## -struct-fields




### -field u

Specifies a union of structures, one for each value of <b>FunctionNumber</b>. The applicable submembers of <b>u</b> for each request are described with each request type in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537211">IEEE 1394 Bus I/O Requests</a>.
<table>
<tr>
<th>FunctionNumber</th>
<th>Associated Member</th>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>
</td>
<td>AllocateAddressRange</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537633">REQUEST_ASYNC_LOCK</a>
</td>
<td>AsyncLock</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537634">REQUEST_ASYNC_READ</a>
</td>
<td>AsyncRead</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537635">REQUEST_ASYNC_STREAM</a>
</td>
<td>AsyncStream</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537636">REQUEST_ASYNC_WRITE</a>
</td>
<td>AsyncWrite</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537647">REQUEST_ISOCH_ALLOCATE_BANDWIDTH</a>
</td>
<td>IsochAllocateBandwidth</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537651">REQUEST_ISOCH_DETACH_BUFFERS</a>
</td>
<td>IsochDetachBuffers</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a>
</td>
<td>IsochListen</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/gg266405">REQUEST_ISOCH_MODIFY_STREAM_PROPERTIES</a>
</td>
<td>IsochModifyStreamProperties</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537657">REQUEST_ISOCH_QUERY_RESOURCES</a>
</td>
<td>IsochQueryResources</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537658">REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH</a>
</td>
<td>IsochSetChannelBandwidth</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537640">REQUEST_FREE_ADDRESS_RANGE</a>
</td>
<td>FreeAddressRange</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/gg266404">REQUEST_GET_CONFIG_ROM</a>
</td>
<td>GetConfigRom</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>
</td>
<td>GetLocalHostInformation</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537645">REQUEST_GET_SPEED_BETWEEN_DEVICES</a>
</td>
<td>GetMaxSpeedBetweenDevices</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>
</td>
<td>GetSpeedTopologyMaps</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537661">REQUEST_SEND_PHY_CONFIG_PACKET</a>
</td>
<td>SendPhyConfigurationPacket</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/gg266407">REQUEST_SEND_PHY_PACKET</a>
</td>
<td>SendPhyPacket</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537663">REQUEST_SET_LOCAL_HOST_PROPERTIES</a>
</td>
<td>SetLocalHostProperties</td>
</tr>
<tr>
<td>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537662">REQUEST_SET_DEVICE_XMIT_PROPERTIES</a>
</td>
<td>SetDeviceXmitProperties</td>
</tr>
<tr>
<td>
<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ieee/device-driver-interface--ddi--changes-in-windows-7">REQUEST_RECEIVE_PHY_PACKET</a>
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

 


### -field FunctionNumber

Determines the type of request. Each request type is documented under the value of <b>FunctionNumber</b> in <a href="https://msdn.microsoft.com/library/windows/hardware/ff537211">IEEE 1394 Bus I/O Requests</a>.


### -field Flags

Reserved. Drivers must set this member to zero with one exception. When making a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537647">REQUEST_ISOCH_ALLOCATE_BANDWIDTH</a> request, the caller can set the IRB_FLAG_ALLOW_REMOTE_FREE flag in <b>Flags</b> to indicate that the system should free the bandwidth handle memory pointed to be <b>IsochAllocateBandwidth.hBandwidth</b>. If caller does not set this flag, then caller will have to free the bandwidth handle. 


### -field BusReserved

Reserved. 


### -field PortReserved

Reserved. 


## -remarks


The <b>Parameters-&gt;Others.Arguments1</b> member of an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537232">IOCTL_1394_CLASS</a> IRP points to an IRB structure. The bus driver uses the IRB to determine the type of request made by the device driver, and also to return the results of the operation. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537211">IEEE 1394 Bus I/O Requests</a> for a description of the behavior of each request.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537232">IOCTL_1394_CLASS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20IRB structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

