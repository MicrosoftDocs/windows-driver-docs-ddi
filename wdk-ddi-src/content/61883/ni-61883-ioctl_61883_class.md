---
UID: NI:61883.IOCTL_61883_CLASS
title: IOCTL_61883_CLASS
author: windows-driver-content
description: An IEC-61883 client driver uses the IRP_MJ_INTERNAL_DEVICE_CONTROL IRP with IoControlCode IOCTL_61883_CLASS to communicate with 1394 driver stack using the IEC-61883 protocol.
old-location: ieee\ioctl_61883_class.htm
old-project: IEEE
ms.assetid: c73472ee-aa27-4256-aa58-9331312ad513
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 61883/IOCTL_61883_CLASS, 61883_requests_a47ccc46-e231-4e3e-8a71-97e4a79143e4.xml, IEEE.ioctl_61883_class, IOCTL_61883_CLASS, IOCTL_61883_CLASS control code [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	61883.h
api_name:
-	IOCTL_61883_CLASS
product: Windows
targetos: Windows
req.typenames: CMP_PLUG_TYPE
---

# IOCTL_61883_CLASS IOCTL


## -description



     An IEC-61883 client driver uses the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP with <b>IoControlCode</b> IOCTL_61883_CLASS to communicate with 1394 driver stack using the IEC-61883 protocol. The driver has access to all operations provided by the IEC-61883 protocol driver through this request.


## -ioctlparameters




### -input-buffer

<b>Parameters-&gt;Others.Argument1</b> points to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a> structure. The <b>Function</b> member of the request structure specifies the type of request. The union member of the request structure specifies the request-type-specific parameters of the request. The parameters and their meaning are documented with each request.


### -input-buffer-length



<text></text>




### -output-buffer

<b>Parameters-&gt;Others.Argument1</b> points to the AV_61883_REQUEST structure passed as input. As part of completing the request, the bus driver fills in certain submembers of the union within the request structure with information for the driver. The returned information is documented with each request.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The information the IEC-61883 protocol driver returns in the I/O Status Block is documented with each request.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537008">AV_61883_REQUEST</a>
 

 

