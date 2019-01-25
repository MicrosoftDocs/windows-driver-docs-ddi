---
UID: NS:ntddcdrm._CDROM_PERFORMANCE_REQUEST
title: "_CDROM_PERFORMANCE_REQUEST" (ntddcdrm.h)
description: The CDROM_PERFORMANCE_REQUEST structure is used as an input parameter to the IOCTL_CDROM_GET_PERFORMANCE I/O control request and describes the performance data requested.
old-location: storage\cdrom_performance_request.htm
tech.root: storage
ms.assetid: E43D2F2C-B5A1-4724-AEBC-F4B6A85EA846
ms.date: 03/29/2018
ms.keywords: "*PCDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST, CDROM_PERFORMANCE_REQUEST structure [Storage Devices], PCDROM_PERFORMANCE_REQUEST, PCDROM_PERFORMANCE_REQUEST structure pointer [Storage Devices], _CDROM_PERFORMANCE_REQUEST, ntddcdrm/CDROM_PERFORMANCE_REQUEST, ntddcdrm/PCDROM_PERFORMANCE_REQUEST, storage.cdrom_performance_request"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdrm.h
api_name:
-	CDROM_PERFORMANCE_REQUEST
product:
- Windows
targetos: Windows
req.typenames: CDROM_PERFORMANCE_REQUEST, *PCDROM_PERFORMANCE_REQUEST
---

# _CDROM_PERFORMANCE_REQUEST structure


## -description


The <b>CDROM_PERFORMANCE_REQUEST</b> structure is used as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a> I/O control request and describes the performance data requested.


## -struct-fields




### -field RequestType

The <a href="https://msdn.microsoft.com/library/windows/hardware/gg441234">CDROM_PERFORMANCE_REQUEST_TYPE</a> enumeration specifies the request type, <b>CdromPerformanceRequest</b>, or <b>CdromWriteSpeedRequest</b>.


### -field PerformanceType

The <a href="https://msdn.microsoft.com/library/windows/hardware/gg441236">CDROM_PERFORMANCE_TYPE</a> enumeration specifies the type of performance data.


### -field Exceptions

The <a href="https://msdn.microsoft.com/library/windows/hardware/gg441231">CDROM_PERFORMANCE_EXCEPTION_TYPE</a>    enumeration specifies the type of exception. 


### -field Tolerance

The <a href="https://msdn.microsoft.com/library/windows/hardware/gg441235">CDROM_PERFORMANCE_TOLERANCE_TYPE</a> enumeration specifies the performance tolerance for the nominal performance and the time tolerance (seek delay) for the exception list.


### -field StaringLba

 




#### - StartingLba

The starting logical block address field.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a>
 

 

