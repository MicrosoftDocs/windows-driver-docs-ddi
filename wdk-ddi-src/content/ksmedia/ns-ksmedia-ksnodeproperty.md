---
UID: NS:ksmedia.KSNODEPROPERTY
title: KSNODEPROPERTY
author: windows-driver-content
description: The KSNODEPROPERTY structure specifies a node and a property of that node.
old-location: audio\ksnodeproperty.htm
old-project: audio
ms.assetid: bbcf7597-217a-499b-b0f2-deef1e85becc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSNODEPROPERTY, KSNODEPROPERTY, KSNODEPROPERTY structure [Audio Devices], PKSNODEPROPERTY, PKSNODEPROPERTY structure pointer [Audio Devices], aud-prop_7d1e6907-77f6-445d-ba5d-b94037b234f3.xml, audio.ksnodeproperty, ksmedia/KSNODEPROPERTY, ksmedia/PKSNODEPROPERTY"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSNODEPROPERTY
product: Windows
targetos: Windows
req.typenames: KSNODEPROPERTY, *PKSNODEPROPERTY
---

# KSNODEPROPERTY structure


## -description


The KSNODEPROPERTY structure specifies a node and a property of that node.


## -syntax


````
typedef struct {
  KSPROPERTY Property;
  ULONG      NodeId;
  ULONG      Reserved;
} KSNODEPROPERTY, *PKSNODEPROPERTY;
````


## -struct-fields




### -field Property

Specifies the property to get or set. This member is a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>.


### -field NodeId

Specifies the node ID. This member identifies the target node for the property request.


### -field Reserved

Reserved for internal use by operating system. Do not use.


## -remarks



This structure is identical to <a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>.

See the discussion of the KSNODEPROPERTY structure in <a href="https://msdn.microsoft.com/dcfd139c-fca3-4068-8324-aa2c952dbc1f">Audio Property Requests</a>.




## -see-also

<a href="..\ks\ns-ks-ksp_node.md">KSP_NODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20KSNODEPROPERTY structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

