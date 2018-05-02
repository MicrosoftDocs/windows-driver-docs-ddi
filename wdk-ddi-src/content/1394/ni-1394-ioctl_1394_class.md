---
UID: NI:1394.IOCTL_1394_CLASS
title: IOCTL_1394_CLASS
author: windows-driver-content
description: An IEEE 1394 driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP, with IoControlCode IOCTL_1394_CLASS, to communicate with the bus driver. The driver has access to all operations provided by the IEEE 1394 bus and its host controller through this request.
old-location: ieee\ioctl_1394_class.htm
old-project: IEEE
ms.assetid: 88a5f5ab-e85b-4bd6-a2f5-bbcdc8c4f30c
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 1394/IOCTL_1394_CLASS, 1394irp_fa8ee811-14ee-44a0-9a9c-b53a421497d4.xml, IEEE.ioctl_1394_class, IOCTL_1394_CLASS, IOCTL_1394_CLASS control, IOCTL_1394_CLASS control code [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	IOCTL_1394_CLASS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_1394_CLASS IOCTL


## -description


An IEEE 1394 driver uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP, with IoControlCode <b>IOCTL_1394_CLASS</b>, to communicate with the bus driver. The driver has access to all operations provided by the IEEE 1394 bus and its host controller through this request.
     


## -ioctlparameters




### -input-buffer

<b>Parameters-&gt;Others.Arguments1</b> points to an <b>IRB</b> structure. The <b>FunctionNumber</b> member of the IRB specifies the type of request. The <b>u</b> member of the IRB is a union that specifies the request-type-specific parameters of the request. The parameters and their meaning are documented with each request.

Legal requests are as follows:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff537632">REQUEST_ALLOCATE_ADDRESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537633">REQUEST_ASYNC_LOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537634">REQUEST_ASYNC_READ</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537635">REQUEST_ASYNC_STREAM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537636">REQUEST_ASYNC_WRITE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537637">REQUEST_BUS_RESET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537638">REQUEST_BUS_RESET_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537639">REQUEST_CONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537640">REQUEST_FREE_ADDRESS_RANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537641">REQUEST_GET_ADDR_FROM_DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537642">REQUEST_GET_CONFIGURATION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537643">REQUEST_GET_GENERATION_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537644">REQUEST_GET_LOCAL_HOST_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537645">REQUEST_GET_SPEED_BETWEEN_DEVICES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537646">REQUEST_GET_SPEED_TOPOLOGY_MAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537647">REQUEST_ISOCH_ALLOCATE_BANDWIDTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537648">REQUEST_ISOCH_ALLOCATE_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537649">REQUEST_ISOCH_ALLOCATE_RESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537650">REQUEST_ISOCH_ATTACH_BUFFERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537651">REQUEST_ISOCH_DETACH_BUFFERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537652">REQUEST_ISOCH_FREE_BANDWIDTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537653">REQUEST_ISOCH_FREE_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537654">REQUEST_ISOCH_FREE_RESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537655">REQUEST_ISOCH_LISTEN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537656">REQUEST_ISOCH_QUERY_CYCLE_TIME</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537657">REQUEST_ISOCH_QUERY_RESOURCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537658">REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537659">REQUEST_ISOCH_STOP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537660">REQUEST_ISOCH_TALK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537661">REQUEST_SEND_PHY_CONFIG_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537662">REQUEST_SET_DEVICE_XMIT_PROPERTIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537663">REQUEST_SET_LOCAL_HOST_PROPERTIES</a>



### -input-buffer-length



<text></text>




### -output-buffer

<b>Parameters-&gt;Others.Arguments1</b> points to the <b>IRB</b> structure passed as input. As part of completing the request, the bus driver fills in certain members of the <b>u</b> member with information for the driver. The returned information is documented below with each request.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The information the bus driver returns in the I/O Status Block is documented below with each request.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537241">IOCTL_IEEE1394_API_REQUEST</a>
 

 

