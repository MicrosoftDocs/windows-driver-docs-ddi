---
UID: NF:dsound.IKsPropertySet.Get
title: IKsPropertySet::Get (dsound.h)
description: The Get method retrieves a property identified by a property-set GUID and a property identifier.  This method belongs to IKsPropertySet in dsound.h.
old-location: stream\ikspropertyset_get.htm
tech.root: stream
ms.date: 08/03/2021
keywords: ["IKsPropertySet::Get"]
ms.keywords: Get, Get method [Streaming Media Devices], Get method [Streaming Media Devices],IKsPropertySet interface, IKsPropertySet interface [Streaming Media Devices],Get method, IKsPropertySet.Get, IKsPropertySet::Get, ksproxy/IKsPropertySet::Get, ksproxy_d5ef4576-b05f-466d-8d87-094d97f83e10.xml, stream.ikspropertyset_get
req.header: dsound.h
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
 - dsound/IKsPropertySet::Get
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

# IKsPropertySet::Get (dsound.h)

## -description

The **Get** method retrieves a property identified by a property-set GUID and a property identifier.

## -parameters

### -param rguidPropSet

[in] GUID that identifies the property set.

### -param ulId

[in] Identifier of the property within the property set.

### -param pInstanceData

[in] Pointer to instance data for the property.

### -param ulInstanceLength

[in] Size, in bytes, of the buffer at *InstanceData*.

### -param pPropertyData

[out] Pointer to a buffer that receives the value of the property.

### -param ulDataLength

[in] Size, in bytes, of the buffer at *PropertyData*.

### -param pulBytesReturned

[out] Pointer to a variable that receives the size, in bytes, of the data that **Get** stores in the buffer at *PropertyData*.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

To retrieve a property, allocate a buffer, which **Get** fills with the property. To determine the necessary buffer size, specify **NULL** for *PropertyData* and zero for *DataLength*. The **Get** method returns the required buffer size in *BytesReturned*.

> [!WARNING]
> Dangerous certain consequences of an actionHeader files *ksproxy.h* and *dsound.h* define similar but incompatible versions of the **IKsPropertySet** interface. Applications that require the KS proxy module should use the version defined in *ksproxy.h*. The DirectSound version of **IKsPropertySet** is described in the DirectSound reference pages in the Microsoft Windows SDK documentation. If an application must include both *ksproxy.h* and *dsound.h*, whichever header file the compiler scans first is the one whose definition of **IKsPropertySet** is used by the compiler.

## -see-also

[IKsPropertySet::Set](./nf-dsound-ikspropertyset-set.md)
