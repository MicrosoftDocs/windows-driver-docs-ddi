---
UID: NF:dsound.IKsPropertySet.Set
title: IKsPropertySet::Set (dsound.h)
description: The Set method sets a property identified by a property-set GUID and a property identifier.
old-location: stream\ikspropertyset_set.htm
tech.root: stream
ms.assetid: 959a78e2-b5c8-47b0-97b1-52d9565a6dab
ms.date: 04/23/2018
keywords: ["IKsPropertySet::Set"]
ms.keywords: IKsPropertySet interface [Streaming Media Devices],Set method, IKsPropertySet.Set, IKsPropertySet::Set, Set, Set method [Streaming Media Devices], Set method [Streaming Media Devices],IKsPropertySet interface, ksproxy/IKsPropertySet::Set, ksproxy_957cf2a5-1dc6-4e89-86c5-b2f01d913b66.xml, stream.ikspropertyset_set
req.header: dsound.h
req.include-header: Ksproxy.h, Ksproxy.h, Dsound.h, Ksproxy.h, Ksproxy.h, Dsound.h
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
 - dsound/IKsPropertySet::Set
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPropertySet.Set
---

# IKsPropertySet::Set (dsound.h)


## -description

The <b>Set</b> method sets a property identified by a property-set GUID and a property identifier.

## -parameters

### -param rguidPropSet

### -param ulId

### -param pInstanceData

### -param ulInstanceLength

### -param pPropertyData

### -param ulDataLength

#### - DataLength [in]

Size, in bytes, of the buffer at <i>PropertyData</i>. 


#### - Id [in]

Identifier of the property within the property set. 


#### - InstanceData [in]

Pointer to instance data for the property. 


#### - InstanceLength [in]

Size, in bytes, of the buffer at <i>InstanceData</i>. 


#### - PropSet [in]

GUID that identifies the property set.


#### - PropertyData [in]

Pointer to a buffer that contains the value of the property to set.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

<div class="alert"><b>Warning</b>  <p class="note">Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.

<p class="note">

If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.



</div>
<div> </div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-ikspropertyset-get">IKsPropertySet::Get</a>

