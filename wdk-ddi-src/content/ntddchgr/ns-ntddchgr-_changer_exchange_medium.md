---
UID: NS:ntddchgr._CHANGER_EXCHANGE_MEDIUM
title: "_CHANGER_EXCHANGE_MEDIUM"
author: windows-driver-content
description: The CHANGER_EXCHANGE_MEDIUM structure is used with the IOCTL_CHANGER_EXCHANGE_MEDIUM request to exchange locations of two pieces of media.
old-location: storage\changer_exchange_medium.htm
old-project: storage
ms.assetid: b0f03d83-61d3-4aa1-ae4e-a8bdc9f13a9f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: CHANGER_EXCHANGE_MEDIUM structure [Storage Devices], *PCHANGER_EXCHANGE_MEDIUM, ntddchgr/PCHANGER_EXCHANGE_MEDIUM, PCHANGER_EXCHANGE_MEDIUM structure pointer [Storage Devices], storage.changer_exchange_medium, CHANGER_EXCHANGE_MEDIUM, _CHANGER_EXCHANGE_MEDIUM, structs-changer_4af39195-5fe7-42e2-b8bd-3247391fea3f.xml, ntddchgr/CHANGER_EXCHANGE_MEDIUM, PCHANGER_EXCHANGE_MEDIUM
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
-	CHANGER_EXCHANGE_MEDIUM
product: Windows
targetos: Windows
req.typenames: CHANGER_EXCHANGE_MEDIUM, *PCHANGER_EXCHANGE_MEDIUM
---

# _CHANGER_EXCHANGE_MEDIUM structure


## -description


The CHANGER_EXCHANGE_MEDIUM structure is used with the <a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_exchange_medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a> request to exchange locations of two pieces of media.


## -syntax


````
typedef struct _CHANGER_EXCHANGE_MEDIUM {
  CHANGER_ELEMENT Transport;
  CHANGER_ELEMENT Source;
  CHANGER_ELEMENT Destination1;
  CHANGER_ELEMENT Destination2;
  BOOLEAN         Flip1;
  BOOLEAN         Flip2;
} CHANGER_EXCHANGE_MEDIUM, *PCHANGER_EXCHANGE_MEDIUM;
````


## -struct-fields




#### - Transport

Indicates which transport element to use for the exchange operation. This member contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


#### - Source

Indicates the element that contains the piece of media to be moved. 


#### - Destination1

Indicates the destination of the piece of media originally at <b>Source</b>. 


#### - Destination2

Indicates the destination of the piece of media originally at <b>Destination1</b>. 


#### - Flip1

Indicates, when <b>TRUE</b>, that the piece of media moved to <b>Destination1</b> should be flipped. This member is valid only if the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped. 


#### - Flip2

Indicates, when <b>TRUE</b>, that the medium moved to <b>Destination2</b> should be flipped. This member is valid only if the <b>Features0</b> member of the GET_CHANGER_PARAMETERS structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped.  


## -see-also

<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>

<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>

<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_exchange_medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20CHANGER_EXCHANGE_MEDIUM structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

