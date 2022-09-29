---
UID: NF:ntifs.SecMakeSPNEx2
title: SecMakeSPNEx2 function (ntifs.h)
description: SecMakeSPNEx2 creates a service provider name string that can be used when it communicates with specific security service providers.
old-location: ifsk\secmakespnex2.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SecMakeSPNEx2 function"]
ms.keywords: SecMakeSPNEx2, SecMakeSPNEx2 function [Installable File System Drivers], ifsk.secmakespnex2, ksecddref_be331d16-cc90-4e80-85cd-c2faaecca843.xml, ntifs/SecMakeSPNEx2
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This function is available on Windows Vista, Windows Server 2008, and later versions of the Windows operating systems.
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SecMakeSPNEx2
 - ntifs/SecMakeSPNEx2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecMakeSPNEx2
---

# SecMakeSPNEx2 function

## -description

**SecMakeSPNEx2** creates a service provider name string that can be used when it communicates with specific security service providers.

## -parameters

### -param ServiceClass [in]

A pointer to a Unicode string that specifies the service class for the security service provider.

### -param ServiceName [in]

A pointer to a Unicode string that specifies the service name for the security service provider.

### -param InstanceName [in, optional]

A pointer to an optional Unicode string that specifies the instance name that is used to connect with the security service provider.

### -param InstancePort [in, optional]

Port number for an instance of the service. Use 0 for the default port. If this parameter is zero, the SPN does not include a port number.

### -param Referrer [in, optional]

Pointer to a constant null-terminated string that specifies the DNS name of the host that gave an IP address referral. This parameter is ignored unless the **ServiceName** parameter specifies an IP address.

### -param InTargetInfo [in, optional]

A pointer to a null-terminated string that indicates the target of the context.

### -param Spn [in, out]

A pointer to a Unicode string that receives the security service provider name string that is created by this function.

### -param TotalSize [out, optional]

Pointer to a ULONG that receives the actual length of the SPN created, including the terminating null character.

### -param Allocate [in]

A Boolean variable that indicates if the memory that is used to store the **Spn** Unicode string should be allocated by this function. If this parameter is TRUE, memory for **Spn** will be allocated from paged pool.

### -param IsTargetInfoMarshaled [in]

A Boolean variable that indicates that the caller provided a marshaled **InTargetInfo** structure.  If **IsTargetInfoMarshaled** is TRUE, **InTargetInfo**->Buffer points to a string representation of the CREDENTIAL_TARGET_INFORMATION structure as returned by the **CredMarshalTargetInfo** function.

## -returns

**SecMakeSPNEx2** returns STATUS_SUCCESS on success or one of the following error codes on failure.

| Return code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_OVERFLOW | The **Allocate** parameter was set to false and one of the following conditions occurred: (1) The **Spn** parameter was a NULL pointer. (2) The maximum length for the **Spn** Unicode string parameter was too small. |
| STATUS_INVALID_PARAMETER | A total length of the **Spn** parameter exceeds 65535 bytes. |
| STATUS_NO_MEMORY | The **Allocate** parameter was set to true, but the memory allocation request failed. |

## -remarks

**SecMakeSPNEx2** is an enhanced version of **SecMakeSPNEx**.

## -see-also

[**SecMakeSPN**](nf-ntifs-secmakespn.md)

[**SecMakeSPNEx**](nf-ntifs-secmakespnex.md)
