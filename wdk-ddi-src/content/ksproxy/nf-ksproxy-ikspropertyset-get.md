---
UID: NF:ksproxy.IKsPropertySet.Get
title: IKsPropertySet::Get (ksproxy.h)
description: The Get method retrieves a property identified by a property-set GUID and a property identifier. This method belongs to IKsPropertySet in ksproxy.h.
tech.root: stream
ms.date: 11/17/2022
keywords: ["IKsPropertySet::Get"]
ms.keywords: Get, Get method [Streaming Media Devices], Get method [Streaming Media Devices],IKsPropertySet interface, IKsPropertySet interface [Streaming Media Devices],Get method, IKsPropertySet.Get, IKsPropertySet::Get, ksproxy/IKsPropertySet::Get, ksproxy_d5ef4576-b05f-466d-8d87-094d97f83e10.xml, stream.ikspropertyset_get
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
 - IKsPropertySet::Get
 - ksproxy/IKsPropertySet::Get
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPropertySet::Get
---

## -description

The **Get** method retrieves a property identified by a property-set GUID and a property identifier.

## -parameters

### -param PropSet [in]

GUID that identifies the property set.

### -param Id [in]

Identifier of the property within the property set.

### -param InstanceData [in]

Pointer to instance data for the property.

### -param InstanceLength [in]

Size, in bytes, of the buffer at *InstanceData*.

### -param PropertyData [out]

Pointer to a buffer that receives the value of the property.

### -param DataLength [in]

Size, in bytes, of the buffer at *PropertyData*.

### -param BytesReturned [out]

Pointer to a variable that receives the size, in bytes, of the data that **Get** stores in the buffer at *PropertyData*.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

To retrieve a property, allocate a buffer, which **Get** fills with the property. To determine the necessary buffer size, specify **NULL** for *PropertyData* and zero for *DataLength*. The **Get** method returns the required buffer size in *BytesReturned*.

> [!WARNING]
> Header files *ksproxy.h* and *dsound.h* define similar but incompatible versions of the **IKsPropertySet** interface. Applications that require the KS proxy module should use the version defined in *ksproxy.h*. If an application must include both *ksproxy.h* and *dsound.h*, whichever header file the compiler scans first is the one whose definition of **IKsPropertySet** is used by the compiler.

## -see-also

[IKsPropertySet::Set](/windows-hardware/drivers/ddi/dsound/nf-dsound-ikspropertyset-set)
