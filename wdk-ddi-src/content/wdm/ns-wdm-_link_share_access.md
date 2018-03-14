---
UID: NS:wdm._LINK_SHARE_ACCESS
title: "_LINK_SHARE_ACCESS"
author: windows-driver-content
description: The share access structure used by file systems for only link files.
old-location: kernel\link_share_access.htm
old-project: kernel
ms.assetid: CD9E3356-45C3-4F56-9EB3-45FB4B3F054B
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PLINK_SHARE_ACCESS, LINK_SHARE_ACCESS, LINK_SHARE_ACCESS structure [Kernel-Mode Driver Architecture], PLINK_SHARE_ACCESS, PLINK_SHARE_ACCESS structure pointer [Kernel-Mode Driver Architecture], _LINK_SHARE_ACCESS, kernel.link_share_access, wdm/LINK_SHARE_ACCESS, wdm/PLINK_SHARE_ACCESS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: 
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
-	LINK_SHARE_ACCESS
product: Windows
targetos: Windows
req.typenames: LINK_SHARE_ACCESS, *PLINK_SHARE_ACCESS
req.product: Windows 10 or later.
---

# _LINK_SHARE_ACCESS structure


## -description


The share access structure used by file systems for only link files. 


## -syntax


````
typedef struct _LINK_SHARE_ACCESS {
  ULONG  OpenCount;
  ULONG  Deleters;
  ULONG  SharedDelete;
} LINK_SHARE_ACCESS, *PLINK_SHARE_ACCESS;
````


## -struct-fields




### -field OpenCount

The number of open requests to the file.


### -field Deleters

File associated with the file object has been 
      opened for delete access.


### -field SharedDelete

File associated with the file object has been opened for delete sharing access.


## -see-also

<a href="..\wdm\nf-wdm-iochecklinkshareaccess.md">IoCheckLinkShareAccess</a>



<a href="..\wdm\nf-wdm-iosetlinkshareaccess.md">IoSetLinkShareAccess</a>



 

 


