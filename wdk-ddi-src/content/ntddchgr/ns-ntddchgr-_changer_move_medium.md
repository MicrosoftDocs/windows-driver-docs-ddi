---
UID: NS:ntddchgr._CHANGER_MOVE_MEDIUM
title: "_CHANGER_MOVE_MEDIUM"
author: windows-driver-content
description: The CHANGER_MOVE_MEDIUM structure is used in conjunction with the IOCTL_CHANGER_MOVE_MEDIUM request to move a piece of media from a source element to a destination.
old-location: storage\changer_move_medium.htm
tech.root: storage
ms.assetid: b19c8add-7377-40d2-8496-fcfa166ac143
ms.date: 3/29/2018
ms.keywords: "*PCHANGER_MOVE_MEDIUM, CHANGER_MOVE_MEDIUM, CHANGER_MOVE_MEDIUM structure [Storage Devices], PCHANGER_MOVE_MEDIUM, PCHANGER_MOVE_MEDIUM structure pointer [Storage Devices], _CHANGER_MOVE_MEDIUM, ntddchgr/CHANGER_MOVE_MEDIUM, ntddchgr/PCHANGER_MOVE_MEDIUM, storage.changer_move_medium, structs-changer_866dd781-90cd-41be-84ce-61c16d31a369.xml"
ms.topic: struct
req.header: ntddchgr.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddchgr.h
api_name:
-	CHANGER_MOVE_MEDIUM
product:
- Windows
targetos: Windows
req.typenames: CHANGER_MOVE_MEDIUM, *PCHANGER_MOVE_MEDIUM
---

# _CHANGER_MOVE_MEDIUM structure


## -description


The CHANGER_MOVE_MEDIUM structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559410">IOCTL_CHANGER_MOVE_MEDIUM</a> request to move a piece of media from a source element to a destination. 


## -struct-fields




### -field Transport

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a> that indicates which transport element to use for the move operation. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


### -field Source

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a> that indicates the element that contains the piece of media to be moved to <b>Destination</b>. The <b>ElementType</b> must be <b>ChangerDrive</b>, <b>ChangerTransport</b>, <b>ChangerSlot</b>, or <b>ChangerIEPort</b>.


### -field Destination

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a> that indicates the destination of the piece of media originally at <b>Source</b>. The <b>ElementType</b> must be <b>ChangerDrive</b>, <b>ChangerTransport</b>, <b>ChangerSlot</b>, or <b>ChangerIEPort</b>.


### -field Flip

Indicates, when <b>TRUE</b>, that the piece of media should be flipped. When <b>FALSE</b> the media is not ready to be flipped. This member is valid only if CHANGER_MEDIUM_FLIP is set in the <b>Features0</b> member of the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551436">ChangerMoveMedium</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559410">IOCTL_CHANGER_MOVE_MEDIUM</a>
 

 

