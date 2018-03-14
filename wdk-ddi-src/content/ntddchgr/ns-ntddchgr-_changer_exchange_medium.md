---
UID: NS:ntddchgr._CHANGER_EXCHANGE_MEDIUM
title: "_CHANGER_EXCHANGE_MEDIUM"
author: windows-driver-content
description: The CHANGER_EXCHANGE_MEDIUM structure is used with the IOCTL_CHANGER_EXCHANGE_MEDIUM request to exchange locations of two pieces of media.
old-location: storage\changer_exchange_medium.htm
old-project: storage
ms.assetid: b0f03d83-61d3-4aa1-ae4e-a8bdc9f13a9f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PCHANGER_EXCHANGE_MEDIUM, CHANGER_EXCHANGE_MEDIUM, CHANGER_EXCHANGE_MEDIUM structure [Storage Devices], PCHANGER_EXCHANGE_MEDIUM, PCHANGER_EXCHANGE_MEDIUM structure pointer [Storage Devices], _CHANGER_EXCHANGE_MEDIUM, ntddchgr/CHANGER_EXCHANGE_MEDIUM, ntddchgr/PCHANGER_EXCHANGE_MEDIUM, storage.changer_exchange_medium, structs-changer_4af39195-5fe7-42e2-b8bd-3247391fea3f.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddchgr.h
api_name:
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




### -field Transport

Indicates which transport element to use for the exchange operation. This member contains a structure of type <a href="..\ntddchgr\ns-ntddchgr-_changer_element.md">CHANGER_ELEMENT</a>. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


### -field Source

Indicates the element that contains the piece of media to be moved. 


### -field Destination1

Indicates the destination of the piece of media originally at <b>Source</b>. 


### -field Destination2

Indicates the destination of the piece of media originally at <b>Destination1</b>. 


### -field Flip1

Indicates, when <b>TRUE</b>, that the piece of media moved to <b>Destination1</b> should be flipped. This member is valid only if the <b>Features0</b> member of the <a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped. 


### -field Flip2

Indicates, when <b>TRUE</b>, that the medium moved to <b>Destination2</b> should be flipped. This member is valid only if the <b>Features0</b> member of the GET_CHANGER_PARAMETERS structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped.  


## -see-also

<a href="..\ntddchgr\ni-ntddchgr-ioctl_changer_exchange_medium.md">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>



<a href="..\mcd\nf-mcd-changerexchangemedium.md">ChangerExchangeMedium</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



 

 


