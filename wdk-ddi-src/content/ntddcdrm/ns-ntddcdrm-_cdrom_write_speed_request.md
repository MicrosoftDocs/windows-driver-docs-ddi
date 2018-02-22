---
UID: NS:ntddcdrm._CDROM_WRITE_SPEED_REQUEST
title: "_CDROM_WRITE_SPEED_REQUEST"
author: windows-driver-content
description: The CDROM_WRITE_SPEED_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE IOCTL and for requesting write speed descriptors.
old-location: storage\cdrom_write_speed_request.htm
old-project: storage
ms.assetid: A7F8AFAE-AFFA-4022-8C04-2BF9177FE9EB
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storage.cdrom_write_speed_request, CDROM_WRITE_SPEED_REQUEST, PCDROM_WRITE_SPEED_REQUEST structure pointer [Storage Devices], ntddcdrm/CDROM_WRITE_SPEED_REQUEST, ntddcdrm/PCDROM_WRITE_SPEED_REQUEST, *PCDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST structure [Storage Devices], _CDROM_WRITE_SPEED_REQUEST, PCDROM_WRITE_SPEED_REQUEST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
apiname:
-	CDROM_WRITE_SPEED_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PCDROM_WRITE_SPEED_REQUEST, CDROM_WRITE_SPEED_REQUEST"
---

# _CDROM_WRITE_SPEED_REQUEST structure


## -description


The <b>CDROM_WRITE_SPEED_REQUEST</b> structure is used as an input parameter to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> IOCTL and for requesting write speed descriptors.


## -syntax


````
typedef struct _CDROM_WRITE_SPEED_REQUEST {
  CDROM_PERFORMANCE_REQUEST_TYPE    RequestType;
} CDROM_WRITE_SPEED_REQUEST, *PCDROM_WRITE_SPEED_REQUEST;
````


## -struct-fields




### -field RequestType

As defined in the <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_request_type.md">CDROM_PERFORMANCE_REQUEST_TYPE</a>    enumeration.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_request_type.md">CDROM_PERFORMANCE_REQUEST_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_WRITE_SPEED_REQUEST structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

