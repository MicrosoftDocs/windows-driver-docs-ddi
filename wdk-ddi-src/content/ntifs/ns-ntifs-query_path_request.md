---
UID: NS:ntifs._QUERY_PATH_REQUEST
tech.root: ifsk
title: QUERY_PATH_REQUEST
ms.date: 08/12/2021
targetos: Windows
description: Learn more about the QUERY_PATH_REQUEST structure.
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
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_PATH_REQUEST, *PQUERY_PATH_REQUEST
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_PATH_REQUEST
 - PQUERY_PATH_REQUEST
 - QUERY_PATH_REQUEST
f1_keywords:
 - _QUERY_PATH_REQUEST
 - ntifs/_QUERY_PATH_REQUEST
 - PQUERY_PATH_REQUEST
 - ntifs/PQUERY_PATH_REQUEST
 - QUERY_PATH_REQUEST
 - ntifs/QUERY_PATH_REQUEST
dev_langs:
 - c++
---

## -description

The **QUERY_PATH_REQUEST** structure contains the prefix resolution request for [**IOCTL_REDIR_QUERY_PATH**](ni-ntifs-ioctl_redir_query_path.md).

## -struct-fields

### -field PathNameLength

The length, in bytes, of the Unicode string contained in the ***FilePathName*** member.

### -field SecurityContext

A pointer to the security context.

### -field FilePathName

A non-NULL terminated Unicode string of the form \\<*server*>\\<*share*>\\<*path*>.

## -see-also

[**IOCTL_REDIR_QUERY_PATH**](ni-ntifs-ioctl_redir_query_path.md)
