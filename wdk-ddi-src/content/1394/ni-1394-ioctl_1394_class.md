---
UID: NI:1394.IOCTL_1394_CLASS
title: IOCTL_1394_CLASS (1394.h)
description: An IEEE 1394 driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP, with IoControlCode IOCTL_1394_CLASS, to communicate with the bus driver. The driver has access to all operations provided by the IEEE 1394 bus and its host controller through this request.
old-location: ieee\ioctl_1394_class.htm
tech.root: IEEE
ms.date: 02/15/2018
keywords: ["IOCTL_1394_CLASS IOCTL"]
ms.keywords: 1394/IOCTL_1394_CLASS, 1394irp_fa8ee811-14ee-44a0-9a9c-b53a421497d4.xml, IEEE.ioctl_1394_class, IOCTL_1394_CLASS, IOCTL_1394_CLASS control, IOCTL_1394_CLASS control code [Buses]
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
req.typenames: 
f1_keywords:
 - IOCTL_1394_CLASS
 - 1394/IOCTL_1394_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - 1394.h
api_name:
 - IOCTL_1394_CLASS
---

# IOCTL_1394_CLASS IOCTL


## -description

An IEEE 1394 driver uses the <a href="/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP, with IoControlCode <b>IOCTL_1394_CLASS</b>, to communicate with the bus driver. The driver has access to all operations provided by the IEEE 1394 bus and its host controller through this request.

## -ioctlparameters

### -input-buffer

<b>Parameters->Others.Arguments1</b> points to an <b>IRB</b> structure. The <b>FunctionNumber</b> member of the IRB specifies the type of request. The <b>u</b> member of the IRB is a union that specifies the request-type-specific parameters of the request. The parameters and their meaning are documented with each request.

Legal requests are as follows:


REQUEST_ALLOCATE_ADDRESS_RANGE



REQUEST_ASYNC_LOCK



REQUEST_ASYNC_READ



REQUEST_ASYNC_STREAM



REQUEST_ASYNC_WRITE



REQUEST_BUS_RESET



REQUEST_BUS_RESET_NOTIFICATION



REQUEST_CONTROL



REQUEST_FREE_ADDRESS_RANGE



REQUEST_GET_ADDR_FROM_DEVICE_OBJECT



REQUEST_GET_CONFIGURATION_INFO



REQUEST_GET_GENERATION_COUNT



REQUEST_GET_LOCAL_HOST_INFO



REQUEST_GET_SPEED_BETWEEN_DEVICES



REQUEST_GET_SPEED_TOPOLOGY_MAPS



REQUEST_ISOCH_ALLOCATE_BANDWIDTH



REQUEST_ISOCH_ALLOCATE_CHANNEL



REQUEST_ISOCH_ALLOCATE_RESOURCES



REQUEST_ISOCH_ATTACH_BUFFERS



REQUEST_ISOCH_DETACH_BUFFERS



REQUEST_ISOCH_FREE_BANDWIDTH



REQUEST_ISOCH_FREE_CHANNEL



REQUEST_ISOCH_FREE_RESOURCES



REQUEST_ISOCH_LISTEN



REQUEST_ISOCH_QUERY_CYCLE_TIME



REQUEST_ISOCH_QUERY_RESOURCES



REQUEST_ISOCH_SET_CHANNEL_BANDWIDTH



REQUEST_ISOCH_STOP



REQUEST_ISOCH_TALK



REQUEST_SEND_PHY_CONFIG_PACKET



REQUEST_SET_DEVICE_XMIT_PROPERTIES



REQUEST_SET_LOCAL_HOST_PROPERTIES

### -input-buffer-length

### -output-buffer

<b>Parameters->Others.Arguments1</b> points to the <b>IRB</b> structure passed as input. As part of completing the request, the bus driver fills in certain members of the <b>u</b> member with information for the driver. The returned information is documented below with each request.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The information the bus driver returns in the I/O Status Block is documented below with each request.

## -see-also

IOCTL_IEEE1394_API_REQUEST
