---
UID: NS:ksmedia.KSRTAUDIO_HWREGISTER_PROPERTY
title: KSRTAUDIO_HWREGISTER_PROPERTY
author: windows-driver-content
description: The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure.
old-location: audio\ksrtaudio_hwregister_property.htm
old-project: audio
ms.assetid: 200577b9-44de-45ca-8b4f-904eabb1a4ce
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PKSRTAUDIO_HWREGISTER_PROPERTY, ,, A, D, E, G, H, I, K, KSRTAUDIO_HWREGISTER_PROPERTY, KSRTAUDIO_HWREGISTER_PROPERTY structure [Audio Devices], O, P, PKSRTAUDIO_HWREGISTER_PROPERTY, PKSRTAUDIO_HWREGISTER_PROPERTY structure pointer [Audio Devices], R, S, T, U, W, Y, _, aud-prop_d554442a-4677-4fc6-a305-ef02d5caffef.xml, audio.ksrtaudio_hwregister_property, ksmedia/KSRTAUDIO_HWREGISTER_PROPERTY, ksmedia/PKSRTAUDIO_HWREGISTER_PROPERTY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KSRTAUDIO_HWREGISTER_PROPERTY
product: Windows
targetos: Windows
req.typenames: KSRTAUDIO_HWREGISTER_PROPERTY, *PKSRTAUDIO_HWREGISTER_PROPERTY
---

# KSRTAUDIO_HWREGISTER_PROPERTY structure


## -description


The KSRTAUDIO_HWREGISTRY_PROPERTY structure appends a register base address to a KSPROPERTY structure.  This structure is used by the client to request the hardware position register via <a href="https://msdn.microsoft.com/library/windows/hardware/ff537381">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a> or request the hardware clock register via <a href="https://msdn.microsoft.com/library/windows/hardware/ff537376">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  PVOID      BaseAddress;
} KSRTAUDIO_HWREGISTER_PROPERTY, *PKSRTAUDIO_HWREGISTER_PROPERTY;
````


## -struct-fields




### -field Property

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that the client initializes appropriately prior to calling KSPROPERTY_RTAUDIO_POSITIONREGISTER or KSPROPERTY_RTAUDIO_CLOCKREGISTER.


### -field BaseAddress

Specifies the buffer base address.  Unless the client specifies a base address, this parameter is set to <b>NULL</b>.


## -remarks



The client uses the KSRTAUDIO_HWREGISTER_PROPERTY structure to request the hardware position register or the hardware clock register from the driver.  The driver returns a <a href="..\ksmedia\ns-ksmedia-ksrtaudio_hwregister.md">KSRTAUDIO_HWREGISTER</a> structure containing information about the requested hardware register.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537381">KSPROPERTY_RTAUDIO_POSITIONREGISTER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537376">KSPROPERTY_RTAUDIO_CLOCKREGISTER</a>



<a href="..\ksmedia\ns-ksmedia-ksrtaudio_hwregister.md">KSRTAUDIO_HWREGISTER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSRTAUDIO_HWREGISTER_PROPERTY structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

