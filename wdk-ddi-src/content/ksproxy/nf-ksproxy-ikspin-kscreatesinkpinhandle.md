---
UID: NF:ksproxy.IKsPin.KsCreateSinkPinHandle
title: IKsPin::KsCreateSinkPinHandle (ksproxy.h)
description: The KsCreateSinkPinHandle method creates a pin handle and stores it in the KS pin object.
old-location: stream\ikspin_kscreatesinkpinhandle.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["IKsPin::KsCreateSinkPinHandle"]
ms.keywords: IKsPin interface [Streaming Media Devices],KsCreateSinkPinHandle method, IKsPin.KsCreateSinkPinHandle, IKsPin::KsCreateSinkPinHandle, KsCreateSinkPinHandle, KsCreateSinkPinHandle method [Streaming Media Devices], KsCreateSinkPinHandle method [Streaming Media Devices],IKsPin interface, ksproxy/IKsPin::KsCreateSinkPinHandle, ksproxy_8d4ac125-ae14-4abf-97cb-74fd33e5029c.xml, stream.ikspin_kscreatesinkpinhandle
req.header: ksproxy.h
req.include-header: Ksproxy.h
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
 - IKsPin::KsCreateSinkPinHandle
 - ksproxy/IKsPin::KsCreateSinkPinHandle
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - ksproxy.h
api_name:
 - IKsPin::KsCreateSinkPinHandle
---

# IKsPin::KsCreateSinkPinHandle


## -description

The <b>KsCreateSinkPinHandle</b> method creates a pin handle and stores it in the KS pin object.

## -parameters

### -param Interface [in]


A type reference to a <a href="/windows-hardware/drivers/stream/kspin-interface-structure">KSPIN_INTERFACE</a> structure for the interface that <b>KsCreateSinkPinHandle</b> negotiated for the created pin.

### -param Medium [in]


A type reference to a <a href="/windows-hardware/drivers/stream/kspin-medium-structure">KSPIN_MEDIUM</a> structure for the medium that <b>KsCreateSinkPinHandle</b> negotiated for the created pin.

## -returns

Returns NOERROR if successful; otherwise, returns an error code.

## -remarks

Since the <b>KsCreateSinkPinHandle</b> method uses pass-by-reference variables, it is not necessary to pass pointers to KSPIN_INTERFACE and KSPIN_MEDIUM structures as arguments. 

After <b>KsCreateSinkPinHandle</b> has created a pin handle, you can retrieve the handle by calling the <a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksobject-ksgetobjecthandle">IKsObject::KsGetObjectHandle</a> method.

This method is for proxy use and is not recommended for application use.

## -see-also

<a href="/windows-hardware/drivers/ddi/ksproxy/nf-ksproxy-iksobject-ksgetobjecthandle">IKsObject::KsGetObjectHandle</a>



<a href="/windows-hardware/drivers/stream/kspin-interface-structure">KSPIN_INTERFACE</a>



<a href="/windows-hardware/drivers/stream/kspin-medium-structure">KSPIN_MEDIUM</a>

