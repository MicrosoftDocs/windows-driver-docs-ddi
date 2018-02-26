---
UID: NS:ehstorioctl._ENUM_PDO_RESULTS
title: "_ENUM_PDO_RESULTS"
author: windows-driver-content
description: This structure describes a result set of Physical Device Objects (PDOs) that are enumerated with IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS.
old-location: storage\enum_pdo_results.htm
old-project: storage
ms.assetid: 80553c9e-3e80-4219-8cc0-2bd4dd6fa76b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , *, *PENUM_PDO_RESULTS, ,, D, E, ENUM_PDO_RESULTS, ENUM_PDO_RESULTS structure [Storage Devices], L, M, N, O, P, PENUM_PDO_RESULTS, PENUM_PDO_RESULTS structure pointer [Storage Devices], R, S, T, U, _, _ENUM_PDO_RESULTS, ehstorioctl/ENUM_PDO_RESULTS, ehstorioctl/PENUM_PDO_RESULTS, storage.enum_pdo_results, structs-silo_45277a1e-1ca6-4bce-a952-b26860796f51.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
-	EhStorIoctl.h
apiname:
-	ENUM_PDO_RESULTS
product: Windows
targetos: Windows
req.typenames: ENUM_PDO_RESULTS, *PENUM_PDO_RESULTS
---

# _ENUM_PDO_RESULTS structure


## -description


This structure describes a result set of Physical Device Objects (PDOs) that are enumerated with <a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>.


## -syntax


````
typedef struct _ENUM_PDO_RESULTS {
  ULONG          cEntries;
  ENUM_PDO_ENTRY rgEntries[ANYSIZE_ARRAY];
} ENUM_PDO_RESULTS, *PENUM_PDO_RESULTS;
````


## -struct-fields




### -field cEntries

This member indicates the number of entries in the array of ENUM_PDO_ENTRY structures.


### -field rgEntries

This member contains the array of ENUM_PDO_ENTRY structures.


## -see-also

<a href="..\ehstorioctl\ni-ehstorioctl-ioctl_ehstor_device_enumerate_pdos.md">IOCTL_EHSTOR_DEVICE_ENUMERATE_PDOS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20ENUM_PDO_RESULTS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

