---
UID: NF:ksproxy.IKsPropertySet.QuerySupported
title: IKsPropertySet::QuerySupported (ksproxy.h)
description: The QuerySupported method determines whether a KS object supports a property set and the type of that support.
tech.root: stream
ms.date: 11/17/2022
keywords: ["IKsPropertySet::QuerySupported"]
ms.keywords: IKsPropertySet interface [Streaming Media Devices],QuerySupported method, IKsPropertySet.QuerySupported, IKsPropertySet::QuerySupported, QuerySupported, QuerySupported method [Streaming Media Devices], QuerySupported method [Streaming Media Devices],IKsPropertySet interface, ksproxy/IKsPropertySet::QuerySupported, ksproxy_d89c460f-dbd5-452e-ab26-44a88dc1fc59.xml, stream.ikspropertyset_querysupported
req.header: ksproxy.h
req.include-header: Ksproxy.h, Dsound.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IKsPropertySet::QuerySupported
 - ksproxy/IKsPropertySet::QuerySupported
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPropertySet::QuerySupported
---

## -description

The **QuerySupported** method determines whether a KS object supports a property set and the type of that support.

## -parameters

### -param PropSet [in]

GUID that identifies the property set.

### -param Id [in]

Identifier of the property within the property set.

### -param TypeSupport [out]

Pointer to a variable that receives a bitmask enumerating the flags that indicate the support that the underlying driver provides. A driver can support a bitwise OR combination of the following flags:

| Value | Description |
|---|---|
| KSPROPERTY_SUPPORT_GET | Supports retrieving a property. Use the [IKsPropertySet::Get](./nf-ksproxy-ikspropertyset-get.md) method to retrieve the property. |
| KSPROPERTY_SUPPORT_SET | Supports setting a property. Use the [IKsPropertySet::Set](../dsound/nf-dsound-ikspropertyset-set.md) method to set the property. |

## -returns

Returns NOERROR if successful; otherwise, returns one of the following error codes:

| Return code | Description |
|---|---|
| **E_NOTIMPL** | Property set is not supported. |
| **E_PROP_ID_UNSUPPORTED** | Property identifier (*Id*) is not supported for the specified property set. |
| **E_PROP_SET_UNSUPPORTED** | Property set is not supported. |

## -remarks

KS objects include, for example, KS filters, KS pins, and KS clocks.

> [!WARNING]
> Header files *ksproxy.h* and *dsound.h* define similar but incompatible versions of the **IKsPropertySet** interface. Applications that require the KS proxy module should use the version defined in *ksproxy.h*. If an application must include both *ksproxy.h* and *dsound.h*, whichever header file the compiler scans first is the one whose definition of **IKsPropertySet** is used by the compiler.

## -see-also

[IKsPropertySet::Get](./nf-ksproxy-ikspropertyset-get.md)

[IKsPropertySet::Set](../dsound/nf-dsound-ikspropertyset-set.md)