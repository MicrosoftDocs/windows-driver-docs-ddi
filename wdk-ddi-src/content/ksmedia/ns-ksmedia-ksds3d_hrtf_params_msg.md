---
UID: NS:ksmedia.KSDS3D_HRTF_PARAMS_MSG
title: KSDS3D_HRTF_PARAMS_MSG
author: windows-driver-content
description: The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).
old-location: audio\ksds3d_hrtf_params_msg.htm
old-project: audio
ms.assetid: e746fc3d-ebfd-41a1-b640-6f803423bd95
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSDS3D_HRTF_PARAMS_MSG, *PKSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG
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
req.alt-api: KSDS3D_HRTF_PARAMS_MSG
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
req.typenames: *PKSDS3D_HRTF_PARAMS_MSG, KSDS3D_HRTF_PARAMS_MSG
---

# KSDS3D_HRTF_PARAMS_MSG structure



## -description
The KSDS3D_HRTF_PARAMS_MSG structure specifies the parameter settings to apply to a head-relative transfer function (HRTF).



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Enabled;
  BOOL  SwapChannels;
  BOOL  ZeroAzimuth;
  BOOL  CrossFadeOutput;
  ULONG FilterSize;
} KSDS3D_HRTF_PARAMS_MSG, *PKSDS3D_HRTF_PARAMS_MSG;
````


## -struct-fields

### -field Size

Specifies the size in bytes of the structure.


### -field Enabled

Specifies whether to enable HRTF processing. If nonzero, HRTF is enabled. If zero, it is disabled.


### -field SwapChannels

Specifies whether the algorithm should swap channels. If <b>TRUE</b>, the algorithm should swap the channels to perform a left-to-right reversal of the location of the source. If <b>FALSE</b>, the algorithm should not swap the channels.


### -field ZeroAzimuth

Specifies whether the azimuth angle is zero. If <b>TRUE</b>, then only half of the filter coefficients are downloaded to the filter because the azimuth angle is zero. If <b>FALSE</b>, all the coefficients are downloaded.


### -field CrossFadeOutput

Specifies whether to cross-fade the output channels after crossing azimuth angle zero. If <b>TRUE</b>, the algorithm should cross-fade the output channels. If <b>FALSE</b>, it should not cross-fade the channels.


### -field FilterSize

Specifies the additional size in bytes of the filter coefficients that are appended to this structure.


## -remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a> property.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537357">KSPROPERTY_HRTF3D_PARAMS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537482">KSPROPSETID_Hrtf3d</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSDS3D_HRTF_PARAMS_MSG structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

