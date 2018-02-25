---
UID: NS:wdm._CLFS_STREAM_ID_INFORMATION
title: "_CLFS_STREAM_ID_INFORMATION"
author: windows-driver-content
description: The CLFS_STREAM_ID_INFORMATION structure holds a value that identifies a stream in a Common Log File System (CLFS) log.
old-location: kernel\clfs_stream_id_information.htm
old-project: kernel
ms.assetid: dc8ea8b0-6aa0-4372-973a-42c545c27e18
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PCLFS_STREAM_ID_INFORMATION, ,, A, C, CLFS_STREAM_ID_INFORMATION, CLFS_STREAM_ID_INFORMATION structure [Kernel-Mode Driver Architecture], D, E, F, I, L, M, N, O, P, PCLFS_STREAM_ID_INFORMATION, PCLFS_STREAM_ID_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLFS_STREAM_ID_INFORMATION, PPCLFS_STREAM_ID_INFORMATION structure pointer [Kernel-Mode Driver Architecture], R, S, T, _, _CLFS_STREAM_ID_INFORMATION, kernel.clfs_stream_id_information, kstruct_a_bfefe413-124f-49c3-8742-c1f1a524f5a6.xml, wdm/CLFS_STREAM_ID_INFORMATION, wdm/PCLFS_STREAM_ID_INFORMATION, wdm/PPCLFS_STREAM_ID_INFORMATION"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20CLFS_STREAM_ID_INFORMATION structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

