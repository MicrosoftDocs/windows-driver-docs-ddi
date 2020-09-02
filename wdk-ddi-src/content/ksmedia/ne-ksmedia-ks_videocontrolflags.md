---
UID: NE:ksmedia.__unnamed_enum_108
title: KS_VideoControlFlags (ksmedia.h)
description: The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.
old-location: stream\ks_videocontrolflags.htm
tech.root: stream
ms.assetid: 7f8b3727-132c-41c8-a252-0f9c8812002f
ms.date: 04/23/2018
keywords: ["KS_VideoControlFlags enumeration"]
ms.keywords: KS_Obsolete_VideoControlFlag_ExternalTriggerEnable, KS_Obsolete_VideoControlFlag_Trigger, KS_VideoControlFlag_ExternalTriggerEnable, KS_VideoControlFlag_FlipHorizontal, KS_VideoControlFlag_FlipVertical, KS_VideoControlFlag_IndependentImagePin, KS_VideoControlFlag_StartPhotoSequenceCapture, KS_VideoControlFlag_StillCapturePreviewFrame, KS_VideoControlFlag_StopPhotoSequenceCapture, KS_VideoControlFlag_Trigger, KS_VideoControlFlags, KS_VideoControlFlags enumeration [Streaming Media Devices], ksmedia/KS_Obsolete_VideoControlFlag_ExternalTriggerEnable, ksmedia/KS_Obsolete_VideoControlFlag_Trigger, ksmedia/KS_VideoControlFlag_ExternalTriggerEnable, ksmedia/KS_VideoControlFlag_FlipHorizontal, ksmedia/KS_VideoControlFlag_FlipVertical, ksmedia/KS_VideoControlFlag_IndependentImagePin, ksmedia/KS_VideoControlFlag_StartPhotoSequenceCapture, ksmedia/KS_VideoControlFlag_StillCapturePreviewFrame, ksmedia/KS_VideoControlFlag_StopPhotoSequenceCapture, ksmedia/KS_VideoControlFlag_Trigger, ksmedia/KS_VideoControlFlags, stream.ks_videocontrolflags, vidcapstruct_ae01591c-4ee4-4e70-bfc2-c78ad73a296f.xml
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
req.typenames: KS_VideoControlFlags
f1_keywords:
 - KS_VideoControlFlags
 - ksmedia/KS_VideoControlFlags
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ksmedia.h
api_name:
 - KS_VideoControlFlags
---

# KS_VideoControlFlags enumeration


## -description

The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.

## -enum-fields

### -field KS_VideoControlFlag_FlipHorizontal

The minidriver is capable of flipping the image horizontally.

### -field KS_VideoControlFlag_FlipVertical

The minidriver is capable of flipping the image vertically.

### -field KS_Obsolete_VideoControlFlag_ExternalTriggerEnable

This value is obsolete. Do not use.

### -field KS_Obsolete_VideoControlFlag_Trigger

This value is obsolete. Do not use.

### -field KS_VideoControlFlag_ExternalTriggerEnable

The minidriver can enable acquisition of a single video frame based on an external trigger. An external trigger typically is hardware-specific.

### -field KS_VideoControlFlag_Trigger

The minidriver can enable acquisition of a single video frame based on a programmatic trigger.

### -field KS_VideoControlFlag_IndependentImagePin

Determines if the image pin is independent of the video pin.

Supported starting with Windows 8.

### -field KS_VideoControlFlag_StillCapturePreviewFrame

Reserved for system use. Do not use in your driver.

Supported starting with Windows 8.

### -field KS_VideoControlFlag_StartPhotoSequenceCapture

Begin photo sequence capture operation.

Supported starting with Windows 8.1.

### -field KS_VideoControlFlag_StopPhotoSequenceCapture

Stop photo sequence operation.

Supported starting with Windows 8.1.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_videocontrol_caps_s">KSPROPERTY_VIDEOCONTROL_CAPS_S</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_videocontrol_mode_s">KSPROPERTY_VIDEOCONTROL_MODE_S</a>

