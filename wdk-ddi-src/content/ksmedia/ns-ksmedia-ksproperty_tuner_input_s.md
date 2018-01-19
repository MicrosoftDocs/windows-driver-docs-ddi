---
UID: NS:ksmedia.KSPROPERTY_TUNER_INPUT_S
title: KSPROPERTY_TUNER_INPUT_S
author: windows-driver-content
description: The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs.
old-location: stream\ksproperty_tuner_input_s.htm
old-project: stream
ms.assetid: 02873563-7448-4406-a8ab-599569abbf7e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSPROPERTY_TUNER_INPUT_S, KSPROPERTY_TUNER_INPUT_S, *PKSPROPERTY_TUNER_INPUT_S
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
req.alt-api: KSPROPERTY_TUNER_INPUT_S
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
req.typenames: KSPROPERTY_TUNER_INPUT_S, *PKSPROPERTY_TUNER_INPUT_S
---

# KSPROPERTY_TUNER_INPUT_S structure



## -description
The KSPROPERTY_TUNER_INPUT_S structure describes the input connection index of a tuner device for devices that support multiple inputs.



## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      InputIndex;
} KSPROPERTY_TUNER_INPUT_S, *PKSPROPERTY_TUNER_INPUT_S;
````


## -struct-fields

### -field Property

Specifies an initialized <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field InputIndex

Specifies the connection index to be used as the tuner input. This value should be in the range of 0 through (number of inputs-1).


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567800">PROPSETID_TUNER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565851">KSPROPERTY_TUNER_INPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_TUNER_INPUT_S structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

