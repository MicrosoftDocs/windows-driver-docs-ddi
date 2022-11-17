---
UID: NF:ksproxy.IKsPropertySet.Set
title: IKsPropertySet::Set (ksproxy.h)
description: The Set method sets a property identified by a property-set GUID and a property identifier. This method belongs to IKsPropertySet in ksproxy.h.
tech.root: stream
ms.date: 11/17/2022
keywords: ["IKsPropertySet::Set"]
ms.keywords: IKsPropertySet interface [Streaming Media Devices],Set method, IKsPropertySet.Set, IKsPropertySet::Set, Set, Set method [Streaming Media Devices], Set method [Streaming Media Devices],IKsPropertySet interface, ksproxy/IKsPropertySet::Set, ksproxy_957cf2a5-1dc6-4e89-86c5-b2f01d913b66.xml, stream.ikspropertyset_set
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
 - IKsPropertySet::Set
 - ksproxy/IKsPropertySet::Set
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPropertySet::Set
---

## -description

The **Set** method sets a property identified by a property-set GUID and a property identifier.

## -parameters

### -param PropSet [in]

GUID that identifies the property set.

### -param Id [in]

Identifier of the property within the property set.

### -param InstanceData [in]

Pointer to instance data for the property.

### -param InstanceLength [in]

Size, in bytes, of the buffer at *InstanceData*.

### -param PropertyData [in]

Pointer to a buffer that contains the value of the property to set.

### -param DataLength [in]

Size, in bytes, of the buffer at *PropertyData*.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

> [!WARNING]
> Header files *ksproxy.h* and *dsound.h* define similar but incompatible versions of the **IKsPropertySet** interface. Applications that require the KS proxy module should use the version defined in *ksproxy.h*. If an application must include both *ksproxy.h* and *dsound.h*, whichever header file the compiler scans first is the one whose definition of **IKsPropertySet** is used by the compiler.

## -see-also

[IKsPropertySet::Get](/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspropertyset-get)
