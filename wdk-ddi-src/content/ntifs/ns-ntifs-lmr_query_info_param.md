---
UID: NS:ntifs._LMR_QUERY_INFO_PARAM
tech.root: ifsk
title: LMR_QUERY_INFO_PARAM
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the LMR_QUERY_INFO_PARAM structure.
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
req.typenames: LMR_QUERY_INFO_PARAM, *PLMR_QUERY_INFO_PARAM
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
 - _LMR_QUERY_INFO_PARAM
 - PLMR_QUERY_INFO_PARAM
 - LMR_QUERY_INFO_PARAM
f1_keywords:
 - _LMR_QUERY_INFO_PARAM
 - ntifs/_LMR_QUERY_INFO_PARAM
 - PLMR_QUERY_INFO_PARAM
 - ntifs/PLMR_QUERY_INFO_PARAM
 - LMR_QUERY_INFO_PARAM
 - ntifs/LMR_QUERY_INFO_PARAM
dev_langs:
 - c++
helpviewer_keywords:
 - _LMR_QUERY_INFO_PARAM
---

## -description

The **LMR_QUERY_INFO_PARAM** structure is used to query information about a file system.

## -struct-fields

### -field Operation

A [**LMR_QUERY_INFO_CLASS**](ne-ntifs-lmr_query_info_class.md) enumeration value that specifies the type of information to query.

## -see-also

[**FSCTL_LMR_QUERY_INFO**](ni-ntifs-fsctl_lmr_query_info.md)

[**LMR_QUERY_INFO_CLASS**](ne-ntifs-lmr_query_info_class.md)
