---
UID: NE:ks.KS_SEEKING_FLAGS
title: KS_SEEKING_FLAGS
author: windows-driver-content
description: The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the KSPROPERTY_POSITIONS structure.
old-location: stream\ks_seeking_flags.htm
old-project: stream
ms.assetid: 8e27872e-4f38-4d0e-92bc-5e759a9db195
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ks/KS_SEEKING_SeekToKeyFrame, KS_SEEKING_FLAGS enumeration [Streaming Media Devices], KS_SEEKING_PositioningBitsMask, ks/KS_SEEKING_ReturnTime, KS_SEEKING_SeekToKeyFrame, ks/KS_SEEKING_RelativePositioning, ks/KS_SEEKING_PositioningBitsMask, KS_SEEKING_NoPositioning, ks/KS_SEEKING_NoPositioning, ks/KS_SEEKING_IncrementalPositioning, stream.ks_seeking_flags, KS_SEEKING_AbsolutePositioning, KS_SEEKING_FLAGS, KS_SEEKING_RelativePositioning, KS_SEEKING_IncrementalPositioning, ks-struct_edea1d66-55d6-4705-ae8f-b940946b87e0.xml, ks/KS_SEEKING_FLAGS, KS_SEEKING_ReturnTime, ks/KS_SEEKING_AbsolutePositioning
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KS_SEEKING_FLAGS
product: Windows
targetos: Windows
req.typenames: KS_SEEKING_FLAGS
---

# KS_SEEKING_FLAGS enumeration


## -description


The KS_SEEKING_FLAGS enumeration lists positioning options that can be used in conjunction with the <a href="..\ks\ns-ks-ksproperty_positions.md">KSPROPERTY_POSITIONS</a> structure.


## -syntax


````
typedef enum  { 
  KS_SEEKING_NoPositioning           = 0,
  KS_SEEKING_AbsolutePositioning     = 1,
  KS_SEEKING_RelativePositioning     = 2,
  KS_SEEKING_IncrementalPositioning  = 3,
  KS_SEEKING_PositioningBitsMask     = 0x3,
  KS_SEEKING_SeekToKeyFrame          = 0x4,
  KS_SEEKING_ReturnTime              = 0x8
} KS_SEEKING_FLAGS;
````


## -enum-fields




### -field KS_SEEKING_NoPositioning


### -field KS_SEEKING_AbsolutePositioning


### -field KS_SEEKING_RelativePositioning


### -field KS_SEEKING_IncrementalPositioning


### -field KS_SEEKING_PositioningBitsMask


### -field KS_SEEKING_SeekToKeyFrame


### -field KS_SEEKING_ReturnTime


## -remarks



The minidriver sets these flag values in a <a href="..\ks\ns-ks-ksproperty_positions.md">KSPROPERTY_POSITIONS</a> structure that it then submits in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565185">KSPROPERTY_MEDIASEEKING_POSITIONS</a> property request.




## -see-also

<a href="..\ks\ns-ks-ksproperty_positions.md">KSPROPERTY_POSITIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565185">KSPROPERTY_MEDIASEEKING_POSITIONS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_SEEKING_FLAGS enumeration%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

