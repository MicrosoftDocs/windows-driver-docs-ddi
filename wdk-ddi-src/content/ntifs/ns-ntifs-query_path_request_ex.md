---
UID: NS:ntifs._QUERY_PATH_REQUEST_EX
tech.root: ifsk
title: QUERY_PATH_REQUEST_EX
ms.date: 08/12/2021
targetos: Windows
description: Learn more about the QUERY_PATH_REQUEST_EX structure.
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
req.target-min-winverclnt: windows Vista
req.target-min-winversvr: 
req.target-type: 
req.typenames: QUERY_PATH_REQUEST_EX, *PQUERY_PATH_REQUEST_EX
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _QUERY_PATH_REQUEST_EX
 - PQUERY_PATH_REQUEST_EX
 - QUERY_PATH_REQUEST_EX
f1_keywords:
 - _QUERY_PATH_REQUEST_EX
 - ntifs/_QUERY_PATH_REQUEST_EX
 - PQUERY_PATH_REQUEST_EX
 - ntifs/PQUERY_PATH_REQUEST_EX
 - QUERY_PATH_REQUEST_EX
 - ntifs/QUERY_PATH_REQUEST_EX
dev_langs:
 - c++
---

## -description

The **QUERY_PATH_REQUEST_EX** structure contains the prefix resolution request for [**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md).

## -struct-fields

### -field pSecurityContext

A pointer to a [**IO_SECURITY_CONTEXT**](../wdm/ns-wdm-_io_security_context.md) structure with the security context.

### -field EaLength

The length, in bytes, of the buffer that **pEaBuffer** points to.

### -field pEaBuffer

A pointer to the extended attributes buffer.

### -field PathName

A non-NULL terminated Unicode string of the form \\<*server*>\\<*share*>\\<*path*>.

### -field DomainServiceName

Pointer to an optional domain service name. Only providers that register as **FSRTL_UNC_PROVIDER_FLAGS_DOMAIN_SVC_AWARE** will see domain service names.

This consumes 2 of the 5 ULONG_PTRs initially reserved in the  [**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md) query.

Available starting in Windows 7.

### -field EcpList

Pointer to an optional [**ECP_LIST**](/previous-versions/windows/hardware/drivers/ff540148(v=vs.85)) structure that contains the extra create parameter (ECP) list associated with the Create IRP that initiated this query path request.

Available starting in Windows 7.

### -field Silo

Pointer to a SILO, associated with the file object on the original IRP. This is required for redirectors to query mini RDR context. This consumes 1 of the 5 ULONG_PTRs initially reserved in the [**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md) query.

### -field Reserved

Reserved for system use.

## -see-also

[**IOCTL_REDIR_QUERY_PATH_EX**](ni-ntifs-ioctl_redir_query_path_ex.md)
