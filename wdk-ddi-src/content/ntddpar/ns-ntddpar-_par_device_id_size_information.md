---
UID: NS:ntddpar._PAR_DEVICE_ID_SIZE_INFORMATION
title: "_PAR_DEVICE_ID_SIZE_INFORMATION"
author: windows-driver-content
description: The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a NULL terminator.
old-location: parports\par_device_id_size_information.htm
old-project: parports
ms.assetid: b48624cd-e8fb-4152-8e34-9cb1e542f62b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PPAR_DEVICE_ID_SIZE_INFORMATION, ,, A, C, D, E, F, I, M, N, O, P, PAR_DEVICE_ID_SIZE_INFORMATION, PAR_DEVICE_ID_SIZE_INFORMATION structure [Parallel Ports], PPAR_DEVICE_ID_SIZE_INFORMATION, PPAR_DEVICE_ID_SIZE_INFORMATION structure pointer [Parallel Ports], R, S, T, V, Z, _, _PAR_DEVICE_ID_SIZE_INFORMATION, cisspd_388a088d-9dd7-4a6c-99ad-b1e725d91f72.xml, ntddpar/PAR_DEVICE_ID_SIZE_INFORMATION, ntddpar/PPAR_DEVICE_ID_SIZE_INFORMATION, parports.par_device_id_size_information"
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
-	PAR_DEVICE_ID_SIZE_INFORMATION
product: Windows
targetos: Windows
req.typenames: PAR_DEVICE_ID_SIZE_INFORMATION, *PPAR_DEVICE_ID_SIZE_INFORMATION
---

# _PAR_DEVICE_ID_SIZE_INFORMATION structure


## -description


The PAR_DEVICE_ID_SIZE_INFORMATION structure specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a <b>NULL</b> terminator.


## -syntax


````
typedef struct _PAR_DEVICE_ID_SIZE_INFORMATION {
  ULONG DeviceIdSize;
} PAR_DEVICE_ID_SIZE_INFORMATION, *PPAR_DEVICE_ID_SIZE_INFORMATION;
````


## -struct-fields




### -field DeviceIdSize

Specifies the size, in bytes, of a buffer that can hold the IEEE 1284 device ID of a parallel device and a <b>NULL</b> terminator.


## -see-also

<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id.md">IOCTL_PAR_QUERY_DEVICE_ID</a>



<a href="..\ntddpar\ni-ntddpar-ioctl_par_query_device_id_size.md">IOCTL_PAR_QUERY_DEVICE_ID_SIZE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20PAR_DEVICE_ID_SIZE_INFORMATION structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

