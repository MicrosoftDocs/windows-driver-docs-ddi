---
UID: NS:ntifs._QUERY_PATH_RESPONSE
tech.root: ifsk
title: QUERY_PATH_RESPONSE
ms.date: 08/12/2021
targetos: Windows
description: Learn more about the QUERY_PATH_RESPONSE structure.
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
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_PATH_RESPONSE, *PQUERY_PATH_RESPONSE
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_PATH_RESPONSE
 - PQUERY_PATH_RESPONSE
 - QUERY_PATH_RESPONSE
f1_keywords:
 - _QUERY_PATH_RESPONSE
 - ntifs/_QUERY_PATH_RESPONSE
 - PQUERY_PATH_RESPONSE
 - ntifs/PQUERY_PATH_RESPONSE
 - QUERY_PATH_RESPONSE
 - ntifs/QUERY_PATH_RESPONSE
dev_langs:
 - c++
---

## -description

The **QUERY_PATH_RESPONSE** structure contains the response for an [**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md) (or [**IOCTL_REDIR_QUERY_PATH**](ni-ntifs-ioctl_redir_query_path.md)) prefix resolution query.

## -struct-fields

### -field LengthAccepted

The length, in bytes, of the prefix claimed by the provider from the Unicode string path that is specified in the **PathName** member of the [**QUERY_PATH_REQUEST_EX**](ns-ntifs-query_path_request_ex.md) (or [**IOCTL_REDIR_QUERY_PATH**](ni-ntifs-ioctl_redir_query_path.md)) structure.

## -see-also

[**IOCTL_REDIR_QUERY_PATH**](ni-ntifs-ioctl_redir_query_path.md)

[**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md)

[**QUERY_PATH_REQUEST_EX**](ns-ntifs-query_path_request_ex.md)
