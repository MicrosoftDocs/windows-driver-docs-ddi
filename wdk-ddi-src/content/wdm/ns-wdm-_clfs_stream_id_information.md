---
UID: NS:wdm._CLFS_STREAM_ID_INFORMATION
title: "_CLFS_STREAM_ID_INFORMATION"
author: windows-driver-content
description: The CLFS_STREAM_ID_INFORMATION structure holds a value that identifies a stream in a Common Log File System (CLFS) log.
old-location: kernel\clfs_stream_id_information.htm
old-project: kernel
ms.assetid: dc8ea8b0-6aa0-4372-973a-42c545c27e18
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PCLFS_STREAM_ID_INFORMATION, CLFS_STREAM_ID_INFORMATION, CLFS_STREAM_ID_INFORMATION structure [Kernel-Mode Driver Architecture], PCLFS_STREAM_ID_INFORMATION, PCLFS_STREAM_ID_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLFS_STREAM_ID_INFORMATION, PPCLFS_STREAM_ID_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CLFS_STREAM_ID_INFORMATION, kernel.clfs_stream_id_information, kstruct_a_bfefe413-124f-49c3-8742-c1f1a524f5a6.xml, wdm/CLFS_STREAM_ID_INFORMATION, wdm/PCLFS_STREAM_ID_INFORMATION, wdm/PPCLFS_STREAM_ID_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	CLFS_STREAM_ID_INFORMATION
product: Windows
targetos: Windows
req.typenames: CLFS_STREAM_ID_INFORMATION, *PCLFS_STREAM_ID_INFORMATION, PPCLFS_STREAM_ID_INFORMATION
req.product: Windows 10 or later.
---

# _CLFS_STREAM_ID_INFORMATION structure


## -description


The <b>CLFS_STREAM_ID_INFORMATION</b> structure holds a value that identifies a stream in a Common Log File System (CLFS) log.


## -syntax


````
typedef struct _CLFS_STREAM_ID_INFORMATION {
  UCHAR StreamIdentifier;
} CLFS_STREAM_ID_INFORMATION, *PCLFS_STREAM_ID_INFORMATION, **PPCLFS_STREAM_ID_INFORMATION;
````


## -struct-fields




### -field StreamIdentifier

An 8-bit value that identifies a stream.


## -remarks



A stream identifier is unique within a given CLFS log.




## -see-also

<a href="..\wdm\nf-wdm-clfsquerylogfileinformation.md">ClfsQueryLogFileInformation</a>



 

 


