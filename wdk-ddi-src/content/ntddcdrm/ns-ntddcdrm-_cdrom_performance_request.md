---
UID: NS:ntddcdrm._CDROM_PERFORMANCE_REQUEST
title: "_CDROM_PERFORMANCE_REQUEST"
author: windows-driver-content
description: The CDROM_PERFORMANCE_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request and describes the performance data requested.
old-location: storage\cdrom_performance_request.htm
old-project: storage
ms.assetid: E43D2F2C-B5A1-4724-AEBC-F4B6A85EA846
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdrm/CDROM_PERFORMANCE_REQUEST, ntddcdrm/PCDROM_PERFORMANCE_REQUEST, _CDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST, *PCDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST structure [Storage Devices], PCDROM_PERFORMANCE_REQUEST structure pointer [Storage Devices], PCDROM_PERFORMANCE_REQUEST, storage.cdrom_performance_request
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
-	CDROM_PERFORMANCE_REQUEST
product: Windows
targetos: Windows
req.typenames: "*PCDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST"
---

# _CDROM_PERFORMANCE_REQUEST structure


## -description


The <b>CDROM_PERFORMANCE_REQUEST</b> structure is used as an input parameter to the <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request and describes the performance data requested.


## -syntax


````
typedef struct _CDROM_PERFORMANCE_REQUEST {
  CDROM_PERFORMANCE_REQUEST_TYPE       RequestType;
  CDROM_PERFORMANCE_TYPE               PerformanceType;
  CDROM_PERFORMANCE_EXCEPTION_TYPE     Exceptions;
  CDROM_PERFORMANCE_TOLERANCE_TYPE     Tolerance;
  ULONG                                StartingLba;
} CDROM_PERFORMANCE_REQUEST, *PCDROM_PERFORMANCE_REQUEST;
````


## -struct-fields




### -field RequestType

The <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_request_type.md">CDROM_PERFORMANCE_REQUEST_TYPE</a> enumeration specifies the request type, <b>CdromPerformanceRequest</b>, or <b>CdromWriteSpeedRequest</b>.


### -field PerformanceType

The <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_type.md">CDROM_PERFORMANCE_TYPE</a> enumeration specifies the type of performance data.


### -field Exceptions

The <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_exception_type.md">CDROM_PERFORMANCE_EXCEPTION_TYPE</a>    enumeration specifies the type of exception. 


### -field Tolerance

The <a href="..\ntddcdrm\ne-ntddcdrm-_cdrom_performance_tolerance_type.md">CDROM_PERFORMANCE_TOLERANCE_TYPE</a> enumeration specifies the performance tolerance for the nominal performance and the time tolerance (seek delay) for the exception list.


### -field StaringLba

 



#### - StartingLba

The starting logical block address field.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_REQUEST structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

