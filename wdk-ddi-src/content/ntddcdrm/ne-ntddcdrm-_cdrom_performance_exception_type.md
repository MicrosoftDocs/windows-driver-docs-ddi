---
UID: NE:ntddcdrm._CDROM_PERFORMANCE_EXCEPTION_TYPE
title: "_CDROM_PERFORMANCE_EXCEPTION_TYPE"
author: windows-driver-content
description: The CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration defines the exceptional conditions for performance data.
old-location: storage\cdrom_performance_exception_type.htm
old-project: storage
ms.assetid: 4AD156F8-911F-4D70-8B0E-8BB0D0747470
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_PERFORMANCE_EXCEPTION_TYPE, CDROM_PERFORMANCE_EXCEPTION_TYPE, CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration [Storage Devices], CdromEntirePerformanceList, CdromNominalPerformance, CdromPerformanceExceptionsOnly, PCDROM_PERFORMANCE_EXCEPTION_TYPE, PCDROM_PERFORMANCE_EXCEPTION_TYPE enumeration pointer [Storage Devices], _CDROM_PERFORMANCE_EXCEPTION_TYPE, ntddcdrm/ CdromPerformanceExceptionsOnly, ntddcdrm/CDROM_PERFORMANCE_EXCEPTION_TYPE, ntddcdrm/CdromEntirePerformanceList, ntddcdrm/CdromNominalPerformance, ntddcdrm/PCDROM_PERFORMANCE_EXCEPTION_TYPE, storage.cdrom_performance_exception_type"
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
-	CDROM_PERFORMANCE_EXCEPTION_TYPE
product: Windows
targetos: Windows
req.typenames: CDROM_PERFORMANCE_EXCEPTION_TYPE, *PCDROM_PERFORMANCE_EXCEPTION_TYPE
---

# _CDROM_PERFORMANCE_EXCEPTION_TYPE enumeration


## -description


The <b>CDROM_PERFORMANCE_EXCEPTION_TYPE</b> enumeration defines the exceptional conditions for performance data. It is a member of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure, which is used as an input parameter to the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request. 


## -syntax


````
typedef enum _CDROM_PERFORMANCE_EXCEPTION_TYPE { 
  CdromNominalPerformance             = 1,
  CdromEntirePerformanceList          = 2,
     CdromPerformanceExceptionsOnly   = 3
} CDROM_PERFORMANCE_EXCEPTION_TYPE, *PCDROM_PERFORMANCE_EXCEPTION_TYPE;
````


## -enum-fields




### -field CdromNominalPerformance

Requests nominal performance parameters.


### -field CdromEntirePerformanceList

Requests the entire performance list, as qualified by the <b>StartingLba</b> field of the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a> structure.


### -field CdromPerformanceExceptionsOnly

Requests only performance exceptions that cause the performance to fall outside the nominal.


## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_performance_request.md">CDROM_PERFORMANCE_REQUEST</a>



 

 


