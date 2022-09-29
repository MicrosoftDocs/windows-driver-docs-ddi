---
UID: NF:ntifs.SecMakeSPN
title: SecMakeSPN function (ntifs.h)
description: SecMakeSPN creates a service provider name string that can be used when communicating with specific security service providers.
old-location: ifsk\secmakespn.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SecMakeSPN function"]
ms.keywords: SecMakeSPN, SecMakeSPN function [Installable File System Drivers], ifsk.secmakespn, ksecddref_0225b4c1-8cfd-49cc-a69a-85da507c401e.xml, ntifs/SecMakeSPN
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
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
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SecMakeSPN
 - ntifs/SecMakeSPN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecMakeSPN
---

# SecMakeSPN function

## -description

**SecMakeSPN** creates a service provider name string that can be used when communicating with specific security service providers.

## -parameters

### -param ServiceClass [in]

A pointer to a Unicode string specifying the service class for the security service provider.

### -param ServiceName [in]

A pointer to a Unicode string specifying the service name for the security service provider.

### -param InstanceName [in, optional]

A pointer to an optional Unicode string specifying the instance name for connecting with the security service provider.

### -param InstancePort [in, optional]

Port number for an instance of the service. Use 0 for the default port. If this parameter is zero, the SPN does not include a port number.

### -param Referrer [in, optional]

Pointer to a constant null-terminated string that specifies the DNS name of the host that gave an IP address referral. This parameter is ignored unless the **ServiceName** parameter specifies an IP address.

### -param Spn [in, out]

A pointer to a Unicode string for storing the security service provider name string created by this function.

### -param Length [out, optional]

Pointer to a ULONG that receives the actual length of the SPN created, including the terminating null character.

### -param Allocate [in]

A Boolean variable indicating if the memory for storing the **Spn** Unicode string should be allocated by this function. If this parameter is true, memory for **Spn** will be allocated from paged pool.

## -returns

**SecMakeSPN** returns STATUS_SUCCESS on success or one of the following error codes on failure.

| Return code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_OVERFLOW | The **Allocate** parameter was set to false and one of the following conditions occurred: (1) The **Spn** parameter was a NULL pointer. (2) The maximum length for the **Spn** Unicode string parameter was too small. |
| STATUS_INVALID_PARAMETER | A total length of the **Spn** parameter exceeds 65535 bytes. |
| STATUS_NO_MEMORY | The **Allocate** parameter was set to true, but the memory allocation request failed. |

## -see-also

[**SecMakeSPNEx**](nf-ntifs-secmakespnex.md)

[**SecMakeSPNEx2**](nf-ntifs-secmakespnex2.md)
