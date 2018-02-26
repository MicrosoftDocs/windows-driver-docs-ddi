---
UID: NE:ksmedia.KS_VideoControlFlags
title: KS_VideoControlFlags
author: windows-driver-content
description: The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.
old-location: stream\ks_videocontrolflags.htm
old-project: stream
ms.assetid: 7f8b3727-132c-41c8-a252-0f9c8812002f
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, C, F, K, KS_Obsolete_VideoControlFlag_ExternalTriggerEnable, KS_Obsolete_VideoControlFlag_Trigger, KS_VideoControlFlag_ExternalTriggerEnable, KS_VideoControlFlag_FlipHorizontal, KS_VideoControlFlag_FlipVertical, KS_VideoControlFlag_IndependentImagePin, KS_VideoControlFlag_StartPhotoSequenceCapture, KS_VideoControlFlag_StillCapturePreviewFrame, KS_VideoControlFlag_StopPhotoSequenceCapture, KS_VideoControlFlag_Trigger, KS_VideoControlFlags, KS_VideoControlFlags enumeration [Streaming Media Devices], S, V, _, a, d, e, g, i, ksmedia/KS_Obsolete_VideoControlFlag_ExternalTriggerEnable, ksmedia/KS_Obsolete_VideoControlFlag_Trigger, ksmedia/KS_VideoControlFlag_ExternalTriggerEnable, ksmedia/KS_VideoControlFlag_FlipHorizontal, ksmedia/KS_VideoControlFlag_FlipVertical, ksmedia/KS_VideoControlFlag_IndependentImagePin, ksmedia/KS_VideoControlFlag_StartPhotoSequenceCapture, ksmedia/KS_VideoControlFlag_StillCapturePreviewFrame, ksmedia/KS_VideoControlFlag_StopPhotoSequenceCapture, ksmedia/KS_VideoControlFlag_Trigger, ksmedia/KS_VideoControlFlags, l, n, o, r, s, stream.ks_videocontrolflags, t, vidcapstruct_ae01591c-4ee4-4e70-bfc2-c78ad73a296f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ksmedia.h
apiname:
-	KS_VideoControlFlags
product: Windows
targetos: Windows
req.typenames: KS_VideoControlFlags
---

# KS_VideoControlFlags enumeration


## -description


The KS_VideoControlFlags enumeration defines video control capabilities for a specific stream.


## -syntax


````
typedef enum  { 
  KS_VideoControlFlag_FlipHorizontal                  = 0x0001,
  KS_VideoControlFlag_FlipVertical                    = 0x0002,
  KS_Obsolete_VideoControlFlag_ExternalTriggerEnable  = 0x0010,
  KS_Obsolete_VideoControlFlag_Trigger                = 0x0020,
  KS_VideoControlFlag_ExternalTriggerEnable           = 0x0004,
  KS_VideoControlFlag_Trigger                         = 0x0008,
  KS_VideoControlFlag_IndependentImagePin             = 0x0040,
#if NTDDI_VERSION >= NTDDI_WIN8
  KS_VideoControlFlag_StillCapturePreviewFrame        = 0x0080,
  KS_VideoControlFlag_StartPhotoSequenceCapture       = 0x0100,
  KS_VideoControlFlag_StopPhotoSequenceCapture        = 0x0200

#endif } KS_VideoControlFlags;
````


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

<a href="..\ksmedia\ns-ksmedia-ksproperty_videocontrol_mode_s.md">KSPROPERTY_VIDEOCONTROL_MODE_S</a>



<a href="..\ksmedia\ns-ksmedia-ksproperty_videocontrol_caps_s.md">KSPROPERTY_VIDEOCONTROL_CAPS_S</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_VideoControlFlags enumeration%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

