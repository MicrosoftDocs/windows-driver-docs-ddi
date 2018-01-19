---
UID: NS:ksmedia.KSPROPERTY_CROSSBAR_ROUTE_S
title: KSPROPERTY_CROSSBAR_ROUTE_S
author: windows-driver-content
description: The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin.
old-location: stream\ksproperty_crossbar_route_s.htm
old-project: stream
ms.assetid: 0db68fcd-8661-41d2-ac95-e9b6033e6aa8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_CROSSBAR_ROUTE_S, *PKSPROPERTY_CROSSBAR_ROUTE_S, KSPROPERTY_CROSSBAR_ROUTE_S
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPROPERTY_CROSSBAR_ROUTE_S
req.alt-loc: ksmedia.h
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
req.typenames: *PKSPROPERTY_CROSSBAR_ROUTE_S, KSPROPERTY_CROSSBAR_ROUTE_S
---

# KSPROPERTY_CROSSBAR_ROUTE_S structure



## -description
The KSPROPERTY_CROSSBAR_ROUTE_S structure describes whether a particular routing is possible and specifies the current routing for a pin.



## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      IndexInputPin;
  ULONG      IndexOutputPin;
  ULONG      CanRoute;
} KSPROPERTY_CROSSBAR_ROUTE_S, *PKSPROPERTY_CROSSBAR_ROUTE_S;
````


## -struct-fields

### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field IndexInputPin

Specifies the zero-based index of the input pin for which the query is being made.


### -field IndexOutputPin

Specifies the zero-based index of the output pin for which the query is being made.


### -field CanRoute

Returns whether the minidriver supports routing between the pins specified by <b>IndexInputPin</b> and <b>IndexOutputPin</b>. A nonzero value indicates that routing is supported. If the minidriver does not support routing between the two pins, this value is zero.


## -remarks
If the value of <b>IndexInputPin</b> is (-1) on an audio output pin, then the audio stream should be muted.


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567804">PROPSETID_VIDCAP_CROSSBAR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565126">KSPROPERTY_CROSSBAR_ROUTE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CROSSBAR_ROUTE_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

