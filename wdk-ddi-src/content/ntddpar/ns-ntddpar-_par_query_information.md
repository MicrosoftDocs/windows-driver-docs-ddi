---
UID: NS:ntddpar._PAR_QUERY_INFORMATION
title: _PAR_QUERY_INFORMATION (ntddpar.h)
description: The PAR_QUERY_INFORMATION structure specifies the operating status of a parallel port.
old-location: parports\par_query_information.htm
tech.root: parports
ms.assetid: 3115b0c2-0190-4c5c-8b31-dbafddc9c44d
ms.date: 02/15/2018
keywords: ["_PAR_QUERY_INFORMATION structure"]
ms.keywords: "*PPAR_QUERY_INFORMATION, PAR_QUERY_INFORMATION, PAR_QUERY_INFORMATION structure [Parallel Ports], PPAR_QUERY_INFORMATION, PPAR_QUERY_INFORMATION structure pointer [Parallel Ports], _PAR_QUERY_INFORMATION, cisspd_d7d19b6f-e1a0-4ad7-b0ee-b8e291e63956.xml, ntddpar/PAR_QUERY_INFORMATION, ntddpar/PPAR_QUERY_INFORMATION, parports.par_query_information"
f1_keywords:
 - "ntddpar/PAR_QUERY_INFORMATION"
 - "PAR_QUERY_INFORMATION"
req.header: ntddpar.h
req.include-header: Ntddpar.h
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
- ntddpar.h
api_name:
- PAR_QUERY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: PAR_QUERY_INFORMATION, *PPAR_QUERY_INFORMATION
---

# _PAR_QUERY_INFORMATION structure


## -description


The PAR_QUERY_INFORMATION structure specifies the operating status of a parallel port.


## -syntax


```cpp
typedef struct _PAR_QUERY_INFORMATION {
  UCHAR Status;
} PAR_QUERY_INFORMATION, *PPAR_QUERY_INFORMATION;
```


## -struct-fields




### -field Status

Specifies the operating status of a parallel port. The value of <b>Status</b> is a bitwise OR of one or more of the following flags:





#### PARALLEL_INIT



#### PARALLEL_AUTOFEED



#### PARALLEL_PAPER_EMPTY



#### PARALLEL_OFF_LINE



#### PARALLEL_POWER_OFF



#### PARALLEL_NOT_CONNECTED



#### PARALLEL_BUSY



#### PARALLEL_SELECTED


## -remarks



This structure is used with an <a href="..\ntddpar\ni-ntddpar-ioctl_par_query_information.md">IOCTL_PAR_QUERY_INFORMATION</a> request.




## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_set_information.md">IOCTL_PAR_SET_INFORMATION</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_information.md">IOCTL_PAR_QUERY_INFORMATION</a>



<a href="..\ntddpar\ns-ntddpar-_par_set_information.md">PAR_SET_INFORMATION</a>



 

 


