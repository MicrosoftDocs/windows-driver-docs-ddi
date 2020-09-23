---
UID: NS:ksmedia.__unnamed_struct_125
title: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S (ksmedia.h)
description: Describes image pin control properties in the PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY camera control property set.
old-location: stream\ksproperty_cameracontrol_image_pin_capability_s.htm
tech.root: stream
ms.assetid: AFFCD1E0-A92F-446D-A30E-C41FA8706FC1
ms.date: 04/30/2019
keywords: ["KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure"]
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_EXCLUSIVE_WITH_RECORD, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure [Streaming Media Devices], KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_SEQUENCE_EXCLUSIVE_WITH_RECORD, PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, ksmedia/PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, stream.ksproperty_cameracontrol_image_pin_capability_s"
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
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S, *PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
f1_keywords:
 - PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
 - ksmedia/PKSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
 - KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
 - ksmedia/KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ksmedia.h
api_name:
 - KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S
---

# KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S structure


## -description

Describes image pin control properties in the <b>PROPSETID_VIDCAP_CAMERACONTROL_IMAGE_PIN_CAPABILITY</b> camera control property set.

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

<a href="/windows-hardware/drivers/stream/ksproperty-cameracontrol-image-pin-capability-property">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_PROPERTY</a>