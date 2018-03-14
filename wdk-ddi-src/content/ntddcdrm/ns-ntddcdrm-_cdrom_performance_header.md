---
UID: NS:ntddcdrm._CDROM_PERFORMANCE_HEADER
title: "_CDROM_PERFORMANCE_HEADER"
author: windows-driver-content
description: The CDROM_PERFORMANCE_HEADER structure is used by the IOCTL_CDROM_GET_PERFORMANCE IOCTL to return data. When the request type is CdromPerformanceRequest, the IOCTL returns this header followed by optional descriptors.
old-location: storage\cdrom_performance_header.htm
old-project: storage
ms.assetid: D7B47E18-038E-41B4-85E5-A48931CDCA89
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCDROM_PERFORMANCE_HEADER, CDROM_PERFORMANCE_HEADER, CDROM_PERFORMANCE_HEADER structure [Storage Devices], PCDROM_PERFORMANCE_HEADER, PCDROM_PERFORMANCE_HEADER structure pointer [Storage Devices], _CDROM_PERFORMANCE_HEADER, ntddcdrm/CDROM_PERFORMANCE_HEADER, ntddcdrm/PCDROM_PERFORMANCE_HEADER, storage.cdrom_performance_header"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddcdrm.h
api_name:
-	CDROM_PERFORMANCE_HEADER
product: Windows
targetos: Windows
req.typenames: CDROM_PERFORMANCE_HEADER, *PCDROM_PERFORMANCE_HEADER
---

# _CDROM_PERFORMANCE_HEADER structure


## -description


The CDROM_PERFORMANCE_HEADER structure is used by the  <a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>  IOCTL to  return data.  When the request type is  CdromPerformanceRequest, the IOCTL returns this header followed by optional descriptors. 


## -syntax


````
typedef struct _CDROM_PERFORMANCE_HEADER {
  UCHAR DataLength[4];
  UCHAR  Except  :1;
  UCHAR Write  :1;
  UCHAR Reserved1  :6;
  UCHAR   Reserved2[3];
  UCHAR  Data[0];
} CDROM_PERFORMANCE_HEADER, *PCDROM_PERFORMANCE_HEADER;
````


## -struct-fields




### -field DataLength

The size of the available data (not just the size of returned data). The size does  not include this <b>Datalength</b> field.


### -field Except

The format of the descriptors that follow the header depend on the value in this field. If false (0), the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_nominal_performance_descriptor.md">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a> follows the <b>CDROM_PERFORMANCE_HEADER</b> in the returned data. If true (1),  the <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exception_performance_descriptor.md">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a> follows the <b>CDROM_PERFORMANCE_HEADER</b> in the returned data.


### -field Write

Indicates whether the result data is for read or write performance.  If false (0), it indicates that the result data is for read performance. If true (1), it indicates that the result data is for write performance.


### -field Reserved1

Reserved.


### -field Reserved2

Reserved.


### -field Data

Contains a list of the following records, depending upon the type of request: <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_nominal_performance_descriptor.md">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a>,   
    <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exception_performance_descriptor.md">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a>,   
    <a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_write_speed_descriptor.md">CDROM_WRITE_SPEED_DESCRIPTOR</a>. 



## -see-also

<a href="..\ntddcdrm\ni-ntddcdrm-ioctl_cdrom_get_performance.md">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_write_speed_descriptor.md">CDROM_WRITE_SPEED_DESCRIPTOR</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_exception_performance_descriptor.md">CDROM_EXCEPTION_PERFORMANCE_DESCRIPTOR</a>



<a href="..\ntddcdrm\ns-ntddcdrm-_cdrom_nominal_performance_descriptor.md">CDROM_NOMINAL_PERFORMANCE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CDROM_PERFORMANCE_HEADER structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

