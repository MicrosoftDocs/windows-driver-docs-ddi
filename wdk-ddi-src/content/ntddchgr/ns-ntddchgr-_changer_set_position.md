---
UID: NS:ntddchgr._CHANGER_SET_POSITION
title: _CHANGER_SET_POSITION (ntddchgr.h)
description: The CHANGER_SET_POSITION structure is used in conjunction with theIOCTL_CHANGER_SET_POSITION request to set the changer's robotic transport mechanism to the specified element address.
old-location: storage\changer_set_position.htm
tech.root: storage
ms.assetid: 1c71473a-98db-41a1-9ca5-ce59f345b5f7
ms.date: 03/29/2018
ms.keywords: "*PCHANGER_SET_POSITION, CHANGER_SET_POSITION, CHANGER_SET_POSITION structure [Storage Devices], PCHANGER_SET_POSITION, PCHANGER_SET_POSITION structure pointer [Storage Devices], _CHANGER_SET_POSITION, ntddchgr/CHANGER_SET_POSITION, ntddchgr/PCHANGER_SET_POSITION, storage.changer_set_position, structs-changer_ab07ca33-813d-4b35-b5ce-809c63633ce5.xml"
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
-	CHANGER_SET_POSITION
product:
- Windows
targetos: Windows
req.typenames: CHANGER_SET_POSITION, *PCHANGER_SET_POSITION
---

# _CHANGER_SET_POSITION structure


## -description


The CHANGER_SET_POSITION structure is used in conjunction with the<a href="https://msdn.microsoft.com/library/windows/hardware/ff559425">IOCTL_CHANGER_SET_POSITION</a> request to set the changer's robotic transport mechanism to the specified element address.


## -struct-fields




### -field Transport

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a> that indicates the transport element to move. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


### -field Destination

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a> that indicates the final destination of the transport element. <b>ElementType</b> must be <b>ChangerSlot</b>, <b>ChangerDrive</b>, or <b>ChangerIEPort</b>.


### -field Flip

Indicates, when <b>TRUE</b>, that the <b>Transport</b> should be flipped. When <b>FALSE</b> this member indicates that the transport is not ready to be flipped. This member is applicable only if CHANGER_MEDIUM_FLIP is set in the <b>Features0</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551457">CHANGER_ELEMENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551449">ChangerSetPosition</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554979">GET_CHANGER_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559425">IOCTL_CHANGER_SET_POSITION</a>
 

 

