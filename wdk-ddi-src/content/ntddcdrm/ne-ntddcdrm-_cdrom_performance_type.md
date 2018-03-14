---
UID: NE:ntddcdrm._CDROM_PERFORMANCE_TYPE
title: "_CDROM_PERFORMANCE_TYPE"
author: windows-driver-content
description: The CDROM_PERFORMANCE_TYPE enumeration defines the read and write performance data requests. It is a member of the CDROM_PERFORMANCE_REQUEST structure, which is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request.
old-location: storage\cdrom_performance_type.htm
old-project: storage
ms.assetid: 1039D4CB-11BA-4131-8CCE-7DCEE4B849D3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_PERFORMANCE_TYPE, CDROM_PERFORMANCE_TYPE, CDROM_PERFORMANCE_TYPE enumeration [Storage Devices], CdromReadPerformance, CdromWritePerformance, PCDROM_PERFORMANCE_TYPE, PCDROM_PERFORMANCE_TYPE enumeration pointer [Storage Devices], _CDROM_PERFORMANCE_TYPE, ntddcdrm/ CdromWritePerformance, ntddcdrm/CDROM_PERFORMANCE_TYPE, ntddcdrm/CdromReadPerformance, ntddcdrm/PCDROM_PERFORMANCE_TYPE, storage.cdrom_performance_type"
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
-	Ntddcdrm.h
api_name:
-	CDROM_PERFORMANCE_TYPE
product: Windows
targetos: Windows
req.typenames: CDROM_PERFORMANCE_TYPE, *PCDROM_PERFORMANCE_TYPE
---

# _CDROM_PERFORMANCE_TYPE enumeration


## -description


The <b>CDROM_PERFORMANCE_TYPE</b> enumeration defines the read and write performance data requests. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request. 


## -syntax


````
typedef enum _CDROM_PERFORMANCE_TYPE { 
  CdromReadPerformance     = 1,
    CdromWritePerformance  = 2
} CDROM_PERFORMANCE_TYPE, *PCDROM_PERFORMANCE_TYPE;
````


## -enum-fields




### -field CdromReadPerformance

Requests streaming read performance data.


### -field CdromWritePerformance

Requests streaming write performance data.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

