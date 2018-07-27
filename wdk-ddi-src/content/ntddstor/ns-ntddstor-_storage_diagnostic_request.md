---
UID: NS:ntddstor._STORAGE_DIAGNOSTIC_REQUEST
title: "_STORAGE_DIAGNOSTIC_REQUEST"
author: windows-driver-content
description: Describes a diagnostic request about the storage driver stack. The STORAGE_DIAGNOSTIC_REQUEST structure is provided in the input buffer of an IOCTL_STORAGE_DIAGNOSTIC request.
old-location: storage\storage_diagnostic_request.htm
tech.root: storage
ms.assetid: BAC83B5C-4F14-430D-9CEF-46812FC4DFED
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_DIAGNOSTIC_REQUEST, PSTORAGE_DIAGNOSTIC_REQUEST, PSTORAGE_DIAGNOSTIC_REQUEST structure pointer [Storage Devices], STORAGE_DIAGNOSTIC_REQUEST, STORAGE_DIAGNOSTIC_REQUEST structure [Storage Devices], _STORAGE_DIAGNOSTIC_REQUEST, ntddstor/PSTORAGE_DIAGNOSTIC_REQUEST, ntddstor/STORAGE_DIAGNOSTIC_REQUEST, storage.storage_diagnostic_request"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
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
-	ntddstor.h
api_name:
-	STORAGE_DIAGNOSTIC_REQUEST
product:
- Windows
targetos: Windows
req.typenames: STORAGE_DIAGNOSTIC_REQUEST, *PSTORAGE_DIAGNOSTIC_REQUEST
---

# _STORAGE_DIAGNOSTIC_REQUEST structure


## -description


Describes  a diagnostic request about the storage driver stack. The <b>STORAGE_DIAGNOSTIC_REQUEST</b> structure is provided in the input buffer of an  <a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a> request.


## -struct-fields




### -field Version

Version of this structure.


### -field Size

Specifies the whole size of the structure and the associated data buffer.


### -field Reserved

Reserved for future use.


### -field TargetType

Specifies the request target type. See definitions for <a href="https://msdn.microsoft.com/8BC338FB-7C76-49D3-96E5-0F20C4A250CE">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>.


### -field Level

Specifies the Diagnostic level. See definitions for <a href="https://msdn.microsoft.com/6D705DA8-7F45-4C7A-813F-5AE4F5A1D8ED">STORAGE_DIAGNOSTIC_LEVEL</a>.


## -see-also




<a href="https://msdn.microsoft.com/5F71CCBE-F93F-4DCD-A673-1D6DE49C7400">IOCTL_STORAGE_DIAGNOSTIC</a>



<a href="https://msdn.microsoft.com/68BC990B-DD0C-49CD-95EC-672FD1459B39">STORAGE_DIAGNOSTIC_DATA</a>



<a href="https://msdn.microsoft.com/6D705DA8-7F45-4C7A-813F-5AE4F5A1D8ED">STORAGE_DIAGNOSTIC_LEVEL</a>



<a href="https://msdn.microsoft.com/8BC338FB-7C76-49D3-96E5-0F20C4A250CE">STORAGE_DIAGNOSTIC_TARGET_TYPE</a>
 

 

