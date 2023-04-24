---
UID: NF:ntifs.SecMakeSPNEx
title: SecMakeSPNEx function (ntifs.h)
description: SecMakeSPNEx creates a service provider name string that can be used when communicating with specific security service providers.
old-location: ifsk\secmakespnex.htm
tech.root: ifsk
ms.date: 05/24/2022
keywords: ["SecMakeSPNEx function"]
ms.keywords: SecMakeSPNEx, SecMakeSPNEx function [Installable File System Drivers], ifsk.secmakespnex, ksecddref_3c4441b9-ed78-473f-ac3c-35a644018499.xml, ntifs/SecMakeSPNEx
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This function is only Windows XP
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
 - SecMakeSPNEx
 - ntifs/SecMakeSPNEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Ksecdd.lib
 - Ksecdd.dll
api_name:
 - SecMakeSPNEx
---

# SecMakeSPNEx function

## -description

**SecMakeSPNEx** creates a service provider name string that can be used when communicating with specific security service providers.

## -parameters

### -param ServiceClass [in]

A pointer to a Unicode string specifying the service class for the security service provider.

### -param ServiceName [in]

A pointer to a Unicode string specifying the service name for the security service provider.

### -param InstanceName [in]

A pointer to an optional Unicode string specifying the instance name for connecting with the security service provider.

### -param InstancePort [in, optional]

Port number for an instance of the service. Use 0 for the default port. If this parameter is zero, the SPN does not include a port number.

### -param Referrer [in, optional]

Pointer to a constant null-terminated string that specifies the DNS name of the host that gave an IP address referral. This parameter is ignored unless the **ServiceName** parameter specifies an IP address.

### -param TargetInfo [in, optional]

A pointer to a null-terminated string that indicates the target of the context.

### -param Spn [in, out]

A pointer to a Unicode string for storing the security service provider name string created by this function.

### -param Length [out, optional]

Pointer to a ULONG that receives the actual length of the SPN created, including the terminating null character.

### -param Allocate [in]

A Boolean variable indicating if the memory for storing the **Spn** Unicode string should be allocated by this function. If this parameter is true, memory for **Spn** will be allocated from paged pool.

## -returns

**SecMakeSPNEx** returns STATUS_SUCCESS on success or one of the following error codes on failure.

| Return code | Description |
| ----------- | ----------- |
| STATUS_BUFFER_OVERFLOW | The **Allocate** parameter was set to false and one of the following conditions occurred: (1) The **Spn** parameter was a NULL pointer. (2) The maximum length for the **Spn** Unicode string parameter was too small. |
| STATUS_INVALID_PARAMETER | A total length of the **Spn** parameter exceeds 65535 bytes. |
| STATUS_NO_MEMORY | The **Allocate** parameter was set to true, but the memory allocation request failed. |

## -remarks

**SecMakeSPNEx** is an enhanced version of **SecMakeSPN**.

## -see-also

[**SecMakeSPN**](nf-ntifs-secmakespn.md)

[**SecMakeSPNEx2**](nf-ntifs-secmakespnex2.md)
