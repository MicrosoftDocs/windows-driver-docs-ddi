---
UID: NS:ntifs._WOF_EXTERNAL_INFO
title: "_WOF_EXTERNAL_INFO"
author: windows-driver-content
description: The WOF_EXTERNAL_INFO structure identifies a file backing provider and the overlay service version it supports.
old-location: ifsk\wof_external_info.htm
old-project: ifsk
ms.assetid: 2522CDC6-C23A-4D9C-83BA-389B7D909619
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PWOF_EXTERNAL_INFO, PWOF_EXTERNAL_INFO, PWOF_EXTERNAL_INFO structure pointer [Installable File System Drivers], WOF_EXTERNAL_INFO, WOF_EXTERNAL_INFO structure [Installable File System Drivers], _WOF_EXTERNAL_INFO, ifsk.wof_external_info, ntifs/PWOF_EXTERNAL_INFO, ntifs/WOF_EXTERNAL_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.1 Update.
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
-	ntifs.h
api_name:
-	WOF_EXTERNAL_INFO
product: Windows
targetos: Windows
req.typenames: WOF_EXTERNAL_INFO, *PWOF_EXTERNAL_INFO
---

# _WOF_EXTERNAL_INFO structure


## -description


The <b>WOF_EXTERNAL_INFO</b> structure identifies a file backing provider and  the overlay service version it supports.


## -syntax


````
typedef struct _WOF_EXTERNAL_INFO {
  ULONG Version;
  ULONG Provider;
} WOF_EXTERNAL_INFO, *PWOF_EXTERNAL_INFO;
````


## -struct-fields




### -field Version

The overlay service version. Set to WOF_CURRENT_VERSION. 


### -field Provider

The identifier of the data source provider. Valid provider identifiers  are WOF_PROVIDER_WIM for the Windows Image Format (WIM) provider, and WOF_PROVIDER_FILE for the individual compressed file provider.  WOF_PROVIDER_WIM is available starting with Windows 8.1 Update, WOF_PROVIDER_FILE is available starting with Windows 10.


## -see-also

<a href="..\ntifs\ns-ntifs-_wof_version_info.md">WOF_VERSION_INFO</a>



<a href="..\ntifs\ns-ntifs-_wof_external_file_id.md">WOF_EXTERNAL_FILE_ID</a>



 

 


