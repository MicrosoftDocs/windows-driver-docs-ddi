---
UID: NF:ksproxy.IKsPropertySet.Get
title: IKsPropertySet::Get (ksproxy.h)
description: The Get method retrieves a property identified by a property-set GUID and a property identifier.
old-location: stream\ikspropertyset_get.htm
tech.root: stream
ms.date: 04/23/2018
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

# IKsPropertySet::Get (ksproxy.h)


## -description

The <b>Get</b> method retrieves a property identified by a property-set GUID and a property identifier.

## -parameters

#### - PropSet [in]

GUID that identifies the property set.


#### - Id [in]

Identifier of the property within the property set. 


#### - InstanceData [in]

Pointer to instance data for the property. 


#### - InstanceLength [in]

Size, in bytes, of the buffer at <i>InstanceData</i>. 


#### - PropertyData [out]

Pointer to a buffer that receives the value of the property. 


#### - DataLength [in]

Size, in bytes, of the buffer at <i>PropertyData</i>. 


#### - BytesReturned [out]

Pointer to a variable that receives the size, in bytes, of the data that <b>Get</b> stores in the buffer at <i>PropertyData</i>.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

To retrieve a property, allocate a buffer, which <b>Get</b> fills with the property. To determine the necessary buffer size, specify <b>NULL</b> for <i>PropertyData</i> and zero for <i>DataLength</i>. The <b>Get</b> method returns the required buffer size in <i>BytesReturned</i>. 

<div class="alert"><b>Warning</b>  <p class="note">Header files <i>ksproxy.h</i> and <i>dsound.h</i> define similar but incompatible versions of the <b>IKsPropertySet</b> interface. Applications that require the KS proxy module should use the version defined in <i>ksproxy.h</i>. The DirectSound version of <b>IKsPropertySet</b> is described in the DirectSound reference pages in the Microsoft Windows SDK documentation.

<p class="note">

If an application must include both <i>ksproxy.h</i> and <i>dsound.h</i>, whichever header file the compiler scans first is the one whose definition of <b>IKsPropertySet</b> is used by the compiler.



</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/dsound/nf-dsound-ikspropertyset-set">IKsPropertySet::Set</a>

