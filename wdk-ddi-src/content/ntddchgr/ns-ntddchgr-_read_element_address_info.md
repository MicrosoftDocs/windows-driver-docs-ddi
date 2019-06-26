---
UID: NS:ntddchgr._READ_ELEMENT_ADDRESS_INFO
title: _READ_ELEMENT_ADDRESS_INFO (ntddchgr.h)
description: This structure is to retrieve changer elements based on a search criterion specified in a call to the ChangerQueryVolumeTags routine.
old-location: storage\read_element_address_info.htm
tech.root: storage
ms.assetid: 5fc5b38e-8eef-4ba0-9f29-025df55e4525
ms.date: 03/29/2018
ms.keywords: "*PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO structure pointer [Storage Devices], READ_ELEMENT_ADDRESS_INFO, READ_ELEMENT_ADDRESS_INFO structure [Storage Devices], _READ_ELEMENT_ADDRESS_INFO, ntddchgr/PREAD_ELEMENT_ADDRESS_INFO, ntddchgr/READ_ELEMENT_ADDRESS_INFO, storage.read_element_address_info, structs-changer_5137d1a1-82bb-4333-b555-45bc1c8cc0bf.xml"
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
- READ_ELEMENT_ADDRESS_INFO
product:
- Windows
targetos: Windows
req.typenames: READ_ELEMENT_ADDRESS_INFO, *PREAD_ELEMENT_ADDRESS_INFO
---

# _READ_ELEMENT_ADDRESS_INFO structure


## -description


This structure is to retrieve changer elements based on a search criterion specified in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a> routine. 


## -struct-fields




### -field NumberOfElements

Indicates the number of elements that matched the criteria specified by <b>ActionCode</b> and <b>VolumeTemplateID</b> in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a> structure passed to the driver. If no element matches the criteria, this member is zero.


### -field ElementStatus

Contains an array holding the first <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a> structure that matched the criteria in the CHANGER_SEND_VOLUME_TAG_INFORMATION structure passed to the driver. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>
 

 

