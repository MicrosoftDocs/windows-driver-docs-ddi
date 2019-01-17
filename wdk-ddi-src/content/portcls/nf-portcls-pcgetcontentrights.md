---
UID: NF:portcls.PcGetContentRights
title: PcGetContentRights function
description: The PcGetContentRights function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the DrmGetContentRights function, and its parameter definitions and return value are also identical.
old-location: audio\pcgetcontentrights.htm
tech.root: audio
ms.assetid: a4e8aee0-d3ac-4086-99a3-a0339b198372
ms.date: 05/08/2018
ms.keywords: PcGetContentRights, PcGetContentRights function [Audio Devices], audio.pcgetcontentrights, audpc-routines_0f94b5f4-2667-488d-a191-4cf13a1f3a27.xml, portcls/PcGetContentRights
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetContentRights function in Microsoft Windows XP and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcGetContentRights
product:
- Windows
targetos: Windows
req.typenames: 
---

# PcGetContentRights function


## -description


The <b>PcGetContentRights</b> function retrieves the DRM content rights assigned to a DRM content ID. Note that this function call is identical in operation to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a> function, and its parameter definitions and return value are also identical.


## -parameters




### -param ContentId [in]

Specifies the DRM content ID. This parameter identifies a KS audio stream.


### -param DrmRights [out]

Specifies the DRM content rights that are assigned to the stream that is identified by <i>ContentId</i>. This parameter is a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff536355">DRMRIGHTS</a> structure.


## -returns



See return value definition in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>.




## -remarks



For more information, see the comments in <a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536354">DrmGetContentRights</a>
 

 

