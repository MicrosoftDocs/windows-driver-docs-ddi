---
UID: NS:ntifs._FILE_CASE_SENSITIVE_INFORMATION
title: _FILE_CASE_SENSITIVE_INFORMATION
author: windows-driver-content
description: The FILE_CASE_SENSITIVE_INFORMATION structure is used to query or set per-directory case-sensitive information.
ms.assetid: 4a36d9b7-8ddf-4064-b0bc-d95d6c1fb360
ms.date: 
ms.topic: struct
ms.keywords: _FILE_CASE_SENSITIVE_INFORMATION, FILE_CASE_SENSITIVE_INFORMATION, *PFILE_CASE_SENSITIVE_INFORMATION, 
req.header: ntifs.h
req.include-header:
req.target-type:
req.target- min-winverclnt: Windows 10 (Version 1803)
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: FILE_CASE_SENSITIVE_INFORMATION, *PFILE_CASE_SENSITIVE_INFORMATION
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	ntifs.h
api_name: 
-	_FILE_CASE_SENSITIVE_INFORMATION
product:
-	Windows
targetos: Windows
---

# _FILE_CASE_SENSITIVE_INFORMATION structure

## -description

The **FILE_CASE_SENSITIVE_INFORMATION** structure is used to query or set per-directory case-sensitive information.

## -struct-fields

### -field Flags
Contains one the following values:

Flag|Value|Description
---|---|---
FILE_CS_FLAG_CASE_SENSITIVE_DIR|0x00000001|Specifies the directory is case-sensitive.

## -remarks

## -see-also
