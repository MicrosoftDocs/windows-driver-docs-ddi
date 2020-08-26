---
UID: NS:wdm._LINK_SHARE_ACCESS
title: _LINK_SHARE_ACCESS (wdm.h)
description: The share access structure used by file systems for only link files.
old-location: kernel\link_share_access.htm
tech.root: kernel
ms.assetid: CD9E3356-45C3-4F56-9EB3-45FB4B3F054B
ms.date: 04/30/2018
keywords: ["LINK_SHARE_ACCESS structure"]
ms.keywords: "*PLINK_SHARE_ACCESS, LINK_SHARE_ACCESS, LINK_SHARE_ACCESS structure [Kernel-Mode Driver Architecture], PLINK_SHARE_ACCESS, PLINK_SHARE_ACCESS structure pointer [Kernel-Mode Driver Architecture], _LINK_SHARE_ACCESS, kernel.link_share_access, wdm/LINK_SHARE_ACCESS, wdm/PLINK_SHARE_ACCESS"
f1_keywords:
 - "wdm/LINK_SHARE_ACCESS"
 - "LINK_SHARE_ACCESS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- LINK_SHARE_ACCESS
targetos: Windows
req.typenames: LINK_SHARE_ACCESS, *PLINK_SHARE_ACCESS
---

# _LINK_SHARE_ACCESS structure


## -description


The share access structure used by file systems for only link files. 


## -struct-fields




### -field OpenCount

The number of open requests to the file.


### -field Deleters

File associated with the file object has been 
      opened for delete access.


### -field SharedDelete

File associated with the file object has been opened for delete sharing access.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iochecklinkshareaccess">IoCheckLinkShareAccess</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iosetlinkshareaccess">IoSetLinkShareAccess</a>
 

 

