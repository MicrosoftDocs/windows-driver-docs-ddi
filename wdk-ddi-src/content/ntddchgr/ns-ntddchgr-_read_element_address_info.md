---
UID: NS:ntddchgr._READ_ELEMENT_ADDRESS_INFO
title: _READ_ELEMENT_ADDRESS_INFO (ntddchgr.h)
description: This structure is to retrieve changer elements based on a search criterion specified in a call to the ChangerQueryVolumeTags routine.
old-location: storage\read_element_address_info.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["READ_ELEMENT_ADDRESS_INFO structure"]
ms.keywords: "*PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO, PREAD_ELEMENT_ADDRESS_INFO structure pointer [Storage Devices], READ_ELEMENT_ADDRESS_INFO, READ_ELEMENT_ADDRESS_INFO structure [Storage Devices], _READ_ELEMENT_ADDRESS_INFO, ntddchgr/PREAD_ELEMENT_ADDRESS_INFO, ntddchgr/READ_ELEMENT_ADDRESS_INFO, storage.read_element_address_info, structs-changer_5137d1a1-82bb-4333-b555-45bc1c8cc0bf.xml"
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
targetos: Windows
req.typenames: READ_ELEMENT_ADDRESS_INFO, *PREAD_ELEMENT_ADDRESS_INFO
f1_keywords:
 - _READ_ELEMENT_ADDRESS_INFO
 - ntddchgr/_READ_ELEMENT_ADDRESS_INFO
 - PREAD_ELEMENT_ADDRESS_INFO
 - ntddchgr/PREAD_ELEMENT_ADDRESS_INFO
 - READ_ELEMENT_ADDRESS_INFO
 - ntddchgr/READ_ELEMENT_ADDRESS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddchgr.h
api_name:
 - _READ_ELEMENT_ADDRESS_INFO
 - PREAD_ELEMENT_ADDRESS_INFO
 - READ_ELEMENT_ADDRESS_INFO
---

# _READ_ELEMENT_ADDRESS_INFO structure


## -description

This structure is to retrieve changer elements based on a search criterion specified in a call to the <a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a> routine.

## -struct-fields

### -field NumberOfElements

Indicates the number of elements that matched the criteria specified by <b>ActionCode</b> and <b>VolumeTemplateID</b> in the <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a> structure passed to the driver. If no element matches the criteria, this member is zero.

### -field ElementStatus

Contains an array holding the first <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a> structure that matched the criteria in the CHANGER_SEND_VOLUME_TAG_INFORMATION structure passed to the driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_status">CHANGER_ELEMENT_STATUS</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_send_volume_tag_information">CHANGER_SEND_VOLUME_TAG_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>

