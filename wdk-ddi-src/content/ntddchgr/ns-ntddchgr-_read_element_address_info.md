---
UID: NS:ntddchgr._READ_ELEMENT_ADDRESS_INFO
title: "_READ_ELEMENT_ADDRESS_INFO"
author: windows-driver-content
description: This structure is to retrieve changer elements based on a search criterion specified in a call to the ChangerQueryVolumeTags routine.
old-location: storage\read_element_address_info.htm
old-project: storage
ms.assetid: 5fc5b38e-8eef-4ba0-9f29-025df55e4525
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO structure pointer [Storage Devices], READ_ELEMENT_ADDRESS_INFO, READ_ELEMENT_ADDRESS_INFO structure [Storage Devices], _READ_ELEMENT_ADDRESS_INFO, ntddchgr/PREAD_ELEMENT_ADDRESS_INFO, ntddchgr/READ_ELEMENT_ADDRESS_INFO, storage.read_element_address_info, structs-changer_5137d1a1-82bb-4333-b555-45bc1c8cc0bf.xml"
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
-	READ_ELEMENT_ADDRESS_INFO
product: Windows
targetos: Windows
req.typenames: READ_ELEMENT_ADDRESS_INFO, *PREAD_ELEMENT_ADDRESS_INFO
---

# _READ_ELEMENT_ADDRESS_INFO structure


## -description


This structure is to retrieve changer elements based on a search criterion specified in a call to the <a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a> routine. 


## -syntax


````
typedef struct _READ_ELEMENT_ADDRESS_INFO {
  ULONG                  NumberOfElements;
  CHANGER_ELEMENT_STATUS ElementStatus[1];
} READ_ELEMENT_ADDRESS_INFO, *PREAD_ELEMENT_ADDRESS_INFO;
````


## -struct-fields




### -field NumberOfElements

Indicates the number of elements that matched the criteria specified by <b>ActionCode</b> and <b>VolumeTemplateID</b> in the <a href="..\ntddchgr\ns-ntddchgr-_changer_send_volume_tag_information.md">CHANGER_SEND_VOLUME_TAG_INFORMATION</a> structure passed to the driver. If no element matches the criteria, this member is zero.


### -field ElementStatus

Contains an array holding the first <a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a> structure that matched the criteria in the CHANGER_SEND_VOLUME_TAG_INFORMATION structure passed to the driver. 


## -see-also

<a href="..\mcd\nf-mcd-changerqueryvolumetags.md">ChangerQueryVolumeTags</a>



<a href="..\ntddchgr\ns-ntddchgr-_get_changer_parameters.md">GET_CHANGER_PARAMETERS</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_element_status.md">CHANGER_ELEMENT_STATUS</a>



<a href="..\ntddchgr\ns-ntddchgr-_changer_send_volume_tag_information.md">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>



 

 


