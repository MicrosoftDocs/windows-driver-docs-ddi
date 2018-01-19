---
UID: NE:ntddcdrm._CDROM_PERFORMANCE_REQUEST_TYPE
title: _CDROM_PERFORMANCE_REQUEST_TYPE
author: windows-driver-content
description: The CDROM_PERFORMANCE_REQUEST_TYPE enumeration defines the types of performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location: storage\cdrom_performance_request_type.htm
old-project: storage
ms.assetid: 139D6E9A-36EE-4162-B9C5-12E9D57C7BE7
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _CDROM_PERFORMANCE_REQUEST_TYPE, *PCDROM_PERFORMANCE_REQUEST_TYPE, CDROM_PERFORMANCE_REQUEST_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CDROM_PERFORMANCE_REQUEST_TYPE
req.alt-loc: Ntddcdrm.h
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
req.typenames: *PCDROM_PERFORMANCE_REQUEST_TYPE, CDROM_PERFORMANCE_REQUEST_TYPE
---

# _CDROM_PERFORMANCE_REQUEST_TYPE enumeration



## -description
The CDROM_PERFORMANCE_REQUEST_TYPE enumeration defines the types of performance data requests. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request. 



## -syntax

````
typedef enum _CDROM_PERFORMANCE_REQUEST_TYPE { 
  CdromPerformanceRequest   = 1,
   CdromWriteSpeedRequest   = 2
} CDROM_PERFORMANCE_REQUEST_TYPE, *PCDROM_PERFORMANCE_REQUEST_TYPE;
````


## -enum-fields

### -field CdromPerformanceRequest

Requests streaming performance data.


### -field  CdromWriteSpeedRequest 

Requests the  write speed descriptor.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>
</dt>
<dt>
<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_REQUEST_TYPE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

