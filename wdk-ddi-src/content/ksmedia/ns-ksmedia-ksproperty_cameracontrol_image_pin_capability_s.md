---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
title: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
author: windows-driver-content
description: Describes image pin control properties in the PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY camera control property set.
old-location: stream\ksproperty_cameracontrol_image_pin_capability_s.htm
old-project: stream
ms.assetid: AFFCD1E0-A92F-446D-A30E-C41FA8706FC1
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, ,, A, B, C, E, G, I, K, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_EXCLUSIVE_WITH_RECORD, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure [Streaming Media Devices], KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_SEQUENCE_EXCLUSIVE_WITH_RECORD, L, M, N, O, P, PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure pointer [Streaming Media Devices], R, S, T, Y, _, ksmedia/KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, ksmedia/PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, stream.ksproperty_cameracontrol_image_pin_capability_s"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ksmedia.h
apiname:
-	KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, *PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
---

# KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure


## -description


Describes image pin control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY</b> camera control property set.


## -syntax


````
typedef struct _KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S {
  ULONG Capabilities;
  ULONG Reserved0;
} KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, *PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S;
````


## -struct-fields




### -field Capabilities

Indicates the image pin control capabilities.



#### KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_EXCLUSIVE_WITH_RECORD

If set, the image pin and the record pin cannot function simultaneously.



#### KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_SEQUENCE_EXCLUSIVE_WITH_RECORD

If set, the image pin and the sequence record pin cannot function simultaneously.


### -field Reserved0

Reserved for system use. Do not use in your driver.


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj553706">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

