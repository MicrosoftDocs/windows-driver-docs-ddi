---
UID: NS:ntifs._LMR_QUERY_SESSION_INFO
tech.root: ifsk
title: LMR_QUERY_SESSION_INFO
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the LMR_QUERY_SESSION_INFO structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10 version 1809, and Windows 10 version 2004 and above versions
req.target-min-winversvr: Windows Server 2019
req.target-type: 
req.typenames: LMR_QUERY_SESSION_INFO, *PLMR_QUERY_SESSION_INFO
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _LMR_QUERY_SESSION_INFO
 - PLMR_QUERY_SESSION_INFO
 - LMR_QUERY_SESSION_INFO
f1_keywords:
 - _LMR_QUERY_SESSION_INFO
 - ntifs/_LMR_QUERY_SESSION_INFO
 - PLMR_QUERY_SESSION_INFO
 - ntifs/PLMR_QUERY_SESSION_INFO
 - LMR_QUERY_SESSION_INFO
 - ntifs/LMR_QUERY_SESSION_INFO
dev_langs:
 - c++
helpviewer_keywords:
 - _LMR_QUERY_SESSION_INFO
---

## -description

The **LMR_QUERY_SESSION_INFO** structure is used to return queried session information for a file or directory.

## -struct-fields

### -field SessionId

The session ID of the file or directory.

## -see-also

[**FSCTL_LMR_QUERY_INFO**](ni-ntifs-fsctl_lmr_query_info.md)

[**LMR_QUERY_INFO_CLASS**](ne-ntifs-lmr_query_info_class.md)
