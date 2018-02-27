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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	61883.h
apiname:
-	IOCTL_61883_CLASS
product: Windows
targetos: Windows
req.typenames: CMP_PLUG_TYPE
---

# IOCTL_61883_CLASS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20IOCTL_61883_CLASS control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

