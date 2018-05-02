---
UID: NS:wdm._CLFS_LOG_NAME_INFORMATION
title: "_CLFS_LOG_NAME_INFORMATION"
author: windows-driver-content
description: The CLFS_LOG_NAME_INFORMATION structure holds the name of a Common Log File System (CLFS) stream or log.
old-location: kernel\clfs_log_name_information.htm
old-project: kernel
ms.assetid: 6011a3e9-1de1-4862-b6a4-a3becf3ec3ca
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PCLFS_LOG_NAME_INFORMATION, CLFS_LOG_NAME_INFORMATION, CLFS_LOG_NAME_INFORMATION structure [Kernel-Mode Driver Architecture], PCLFS_LOG_NAME_INFORMATION, PCLFS_LOG_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PPCLFS_LOG_NAME_INFORMATION, PPCLFS_LOG_NAME_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _CLFS_LOG_NAME_INFORMATION, kernel.clfs_log_name_information, kstruct_a_381305d2-8396-4f34-b981-0ba3eb732cd1.xml, wdm/CLFS_LOG_NAME_INFORMATION, wdm/PCLFS_LOG_NAME_INFORMATION, wdm/PPCLFS_LOG_NAME_INFORMATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CLFS_LOG_NAME_INFORMATION
product: Windows
targetos: Windows
req.typenames: CLFS_LOG_NAME_INFORMATION, *PCLFS_LOG_NAME_INFORMATION, PPCLFS_LOG_NAME_INFORMATION
---

# _CLFS_LOG_NAME_INFORMATION structure


## -description


The <b>CLFS_LOG_NAME_INFORMATION</b> structure holds the name of a Common Log File System (CLFS) stream or log.


## -struct-fields




### -field NameLengthInBytes

The size, in bytes, of the log name.


### -field Name

An array of wide characters that holds the log name. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff541679">ClfsQueryLogFileInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541761">ClfsSetLogFileInformation</a>
 

 

