---
UID: NS:ntddchgr._CHANGER_EXCHANGE_MEDIUM
title: _CHANGER_EXCHANGE_MEDIUM (ntddchgr.h)
description: The CHANGER_EXCHANGE_MEDIUM structure is used with the IOCTL_CHANGER_EXCHANGE_MEDIUM request to exchange locations of two pieces of media.
old-location: storage\changer_exchange_medium.htm
tech.root: storage
ms.assetid: b0f03d83-61d3-4aa1-ae4e-a8bdc9f13a9f
ms.date: 03/29/2018
ms.keywords: "*PCHANGER_EXCHANGE_MEDIUM, CHANGER_EXCHANGE_MEDIUM, CHANGER_EXCHANGE_MEDIUM structure [Storage Devices], PCHANGER_EXCHANGE_MEDIUM, PCHANGER_EXCHANGE_MEDIUM structure pointer [Storage Devices], _CHANGER_EXCHANGE_MEDIUM, ntddchgr/CHANGER_EXCHANGE_MEDIUM, ntddchgr/PCHANGER_EXCHANGE_MEDIUM, storage.changer_exchange_medium, structs-changer_4af39195-5fe7-42e2-b8bd-3247391fea3f.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddchgr.h
api_name:
- CHANGER_EXCHANGE_MEDIUM
product:
- Windows
targetos: Windows
req.typenames: CHANGER_EXCHANGE_MEDIUM, *PCHANGER_EXCHANGE_MEDIUM
---

# _CHANGER_EXCHANGE_MEDIUM structure


## -description


The CHANGER_EXCHANGE_MEDIUM structure is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ni-ntddchgr-ioctl_changer_exchange_medium">IOCTL_CHANGER_EXCHANGE_MEDIUM</a> request to exchange locations of two pieces of media.


## -struct-fields




### -field Transport

Indicates which transport element to use for the exchange operation. This member contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>. The <b>ElementType</b> member of the CHANGER_ELEMENT structure must be assigned a value of <b>ChangerTransport</b>. 


### -field Source

Indicates the element that contains the piece of media to be moved. 


### -field Destination1

Indicates the destination of the piece of media originally at <b>Source</b>. 


### -field Destination2

Indicates the destination of the piece of media originally at <b>Destination1</b>. 


### -field Flip1

Indicates, when <b>TRUE</b>, that the piece of media moved to <b>Destination1</b> should be flipped. This member is valid only if the <b>Features0</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped. 


### -field Flip2

Indicates, when <b>TRUE</b>, that the medium moved to <b>Destination2</b> should be flipped. This member is valid only if the <b>Features0</b> member of the GET_CHANGER_PARAMETERS structure is set to CHANGER_MEDIUM_FLIP. When <b>FALSE</b>, this member indicates that the media does not ready to be flipped.  


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mcd/nf-mcd-changerexchangemedium">ChangerExchangeMedium</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ni-ntddchgr-ioctl_changer_exchange_medium">IOCTL_CHANGER_EXCHANGE_MEDIUM</a>
 

 

