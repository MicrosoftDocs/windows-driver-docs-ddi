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
ms.keywords: ",  , *, *PWOF_EXTERNAL_INFO, ,, A, E, F, I, L, N, O, P, PWOF_EXTERNAL_INFO, PWOF_EXTERNAL_INFO structure pointer [Installable File System Drivers], R, T, W, WOF_EXTERNAL_INFO, WOF_EXTERNAL_INFO structure [Installable File System Drivers], X, _, _WOF_EXTERNAL_INFO, ifsk.wof_external_info, ntifs/PWOF_EXTERNAL_INFO, ntifs/WOF_EXTERNAL_INFO"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntifs.h
apiname:
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

<a href="..\ntifs\ns-ntifs-_wof_external_file_id.md">WOF_EXTERNAL_FILE_ID</a>



<a href="..\ntifs\ns-ntifs-_wof_version_info.md">WOF_VERSION_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20WOF_EXTERNAL_INFO structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

