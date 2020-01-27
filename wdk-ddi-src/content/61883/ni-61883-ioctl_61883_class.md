---
UID: NI:61883.IOCTL_61883_CLASS
title: IOCTL_61883_CLASS (61883.h)
description: An IEC-61883 client driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP with IoControlCode IOCTL_61883_CLASS to communicate with 1394 driver stack using the IEC-61883 protocol.
old-location: ieee\ioctl_61883_class.htm
tech.root: IEEE
ms.assetid: c73472ee-aa27-4256-aa58-9331312ad513
ms.date: 02/15/2018
ms.keywords: 61883/IOCTL_61883_CLASS, 61883_requests_a47ccc46-e231-4e3e-8a71-97e4a79143e4.xml, IEEE.ioctl_61883_class, IOCTL_61883_CLASS, IOCTL_61883_CLASS control, IOCTL_61883_CLASS control code [Buses]
f1_keywords:
 - "61883/IOCTL_61883_CLASS"
req.header: 61883.h
req.include-header: 61883.h
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
- 61883.h
api_name:
- IOCTL_61883_CLASS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_61883_CLASS IOCTL


## -description



     An IEC-61883 client driver uses the <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP with <b>IoControlCode</b> IOCTL_61883_CLASS to communicate with 1394 driver stack using the IEC-61883 protocol. The driver has access to all operations provided by the IEC-61883 protocol driver through this request.


## -ioctlparameters




### -input-buffer

<b>Parameters->Others.Argument1</b> points to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a> structure. The <b>Function</b> member of the request structure specifies the type of request. The union member of the request structure specifies the request-type-specific parameters of the request. The parameters and their meaning are documented with each request.


### -input-buffer-length








### -output-buffer

<b>Parameters->Others.Argument1</b> points to the AV_61883_REQUEST structure passed as input. As part of completing the request, the bus driver fills in certain submembers of the union within the request structure with information for the driver. The returned information is documented with each request.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The information the IEC-61883 protocol driver returns in the I/O Status Block is documented with each request.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/61883/ns-61883-_av_61883_request">AV_61883_REQUEST</a>
 

 

