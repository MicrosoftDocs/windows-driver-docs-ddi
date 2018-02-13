---
UID: NS:ntddchgr._CHANGER_MOVE_MEDIUM
title: "_CHANGER_MOVE_MEDIUM"
author: windows-driver-content
description: The CHANGER_MOVE_MEDIUM structure is used in conjunction with the IOCTL_CHANGER_MOVE_MEDIUM request to move a piece of media from a source element to a destination.
old-location: storage\changer_move_medium.htm
old-project: storage
ms.assetid: b19c8add-7377-40d2-8496-fcfa166ac143
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: "*PCHANGER_MOVE_MEDIUM, _CHANGER_MOVE_MEDIUM, PCHANGER_MOVE_MEDIUM, CHANGER_MOVE_MEDIUM, structs-changer_866dd781-90cd-41be-84ce-61c16d31a369.xml, CHANGER_MOVE_MEDIUM structure [Storage Devices], ntddchgr/CHANGER_MOVE_MEDIUM, PCHANGER_MOVE_MEDIUM structure pointer [Storage Devices], storage.changer_move_medium, ntddchgr/PCHANGER_MOVE_MEDIUM"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddchgr.h
apiname:
-	CHANGER_MOVE_MEDIUM
product: Windows
targetos: Windows
req.typenames: "*PCHANGER_MOVE_MEDIUM, CHANGER_MOVE_MEDIUM"
---

# _CHANGER_MOVE_MEDIUM structure


## -description


The CHANGER_MOVE_MEDIUM structure is used in conjunction with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a> request to move a piece of media from a source element to a destination. 


## -syntax


````
typedef struct _CHANGER_MOVE_MEDIUM {
  CHANGER_ELEMENT Transport;
  CHANGER_ELEMENT Source;
  CHANGER_ELEMENT Destination;
  BOOLEAN         Flip;
} CHANGER_MOVE_MEDIUM, *PCHANGER_MOVE_MEDIUM;
````


## -struct-fields




### -field Transport

Contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> that indicates which transport element to use for the move operation. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


### -field Source

Contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> that indicates the element that contains the piece of media to be moved to <b>Destination</b>. The <b>ElementType</b> must be <b>ChangerDrive</b>, <b>ChangerTransport</b>, <b>ChangerSlot</b>, or <b>ChangerIEPort</b>.


### -field Destination

Contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a> that indicates the destination of the piece of media originally at <b>Source</b>. The <b>ElementType</b> must be <b>ChangerDrive</b>, <b>ChangerTransport</b>, <b>ChangerSlot</b>, or <b>ChangerIEPort</b>.


### -field Flip

Indicates, when <b>TRUE</b>, that the piece of media should be flipped. When <b>FALSE</b> the media is not ready to be flipped. This member is valid only if CHANGER_MEDIUM_FLIP is set in the <b>Features0</b> member of the  <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure.


## -see-also

<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>



<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_move_medium.md">IOCTL_CHANGER_MOVE_MEDIUM</a>



<a href="..\mcd\nf-mcd-changermovemedium.md">ChangerMoveMedium</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_MOVE_MEDIUM structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

