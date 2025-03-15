---
UID: NE:ntifs._LMR_QUERY_INFO_CLASS
tech.root: ifsk
title: LMR_QUERY_INFO_CLASS
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the LMR_QUERY_INFO_CLASS enumeration
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10 version 1809, and Windows 10 version 2004 and above versions
req.target-min-winversvr: Windows Server 2019
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _LMR_QUERY_INFO_CLASS
 - PLMR_QUERY_INFO_CLASS
 - LMR_QUERY_INFO_CLASS
f1_keywords:
 - _LMR_QUERY_INFO_CLASS
 - ntifs/_LMR_QUERY_INFO_CLASS
 - PLMR_QUERY_INFO_CLASS
 - ntifs/PLMR_QUERY_INFO_CLASS
 - LMR_QUERY_INFO_CLASS
 - ntifs/LMR_QUERY_INFO_CLASS
dev_langs:
 - c++
helpviewer_keywords:
 - _LMR_QUERY_INFO_CLASS
---

## -description

The **LMR_QUERY_INFO_CLASS** enumeration specifies the type of information to query.

## -enum-fields

### -field LMRQuerySessionInfo:1

Query the session ID information for the file or directory. The information is returned in an [**LMR_QUERY_SESSION_INFO**](ns-ntifs-lmr_query_session_info.md) structure via **OutputBuffer**.

## -see-also

[**FSCTL_LMR_QUERY_INFO**](ni-ntifs-fsctl_lmr_query_info.md)

[**LMR_QUERY_INFO_PARAM**](ns-ntifs-lmr_query_info_param.md)

[**LMR_QUERY_SESSION_INFO**](ns-ntifs-lmr_query_session_info.md)
