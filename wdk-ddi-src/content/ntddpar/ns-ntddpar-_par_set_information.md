---
UID: NS:ntddpar._PAR_SET_INFORMATION
title: _PAR_SET_INFORMATION
author: windows-driver-content
description: The PAR_SET_INFORMATION structure specifies the initial operating status of a parallel port.
old-location: parports\par_set_information.htm
old-project: parports
ms.assetid: 05e889b1-4b18-4122-9332-69778017e15c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ntddpar/PAR_SET_INFORMATION, ntddpar/PPAR_SET_INFORMATION, PPAR_SET_INFORMATION, cisspd_8390a7d0-a4b2-4970-94f8-fd270f2d8256.xml, PPAR_SET_INFORMATION structure pointer [Parallel Ports], parports.par_set_information, _PAR_SET_INFORMATION, PAR_SET_INFORMATION structure [Parallel Ports], *PPAR_SET_INFORMATION, PAR_SET_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntddpar.h
apiname: 
-	PAR_SET_INFORMATION
product: Windows
targetos: Windows
req.typenames: PAR_SET_INFORMATION, *PPAR_SET_INFORMATION
---

# _PAR_SET_INFORMATION structure


## -description


The PAR_SET_INFORMATION structure specifies the initial operating status of a parallel port.


## -syntax


````
typedef struct _PAR_SET_INFORMATION {
  UCHAR Init;
} PAR_SET_INFORMATION, *PPAR_SET_INFORMATION;
````


## -struct-fields




### -field Init

Specifies the operating status of the parallel port. Must be set to PARALLEL_INIT.


## -remarks


This structure is used with an <a href="..\ntddpar\ni-ntddpar-ioctl_par_set_information.md">IOCTL_PAR_SET_INFORMATION</a> request.



## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_information.md">IOCTL_PAR_QUERY_INFORMATION</a>

<a href="..\ntddpar\ns-ntddpar-_par_query_information.md">PAR_QUERY_INFORMATION</a>

<a href="..\ntddpar\ni-ntddpar-ioctl_par_set_information.md">IOCTL_PAR_SET_INFORMATION</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PAR_SET_INFORMATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

