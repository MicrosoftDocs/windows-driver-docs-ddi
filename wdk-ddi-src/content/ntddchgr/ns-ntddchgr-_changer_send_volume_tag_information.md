---
UID: NS:ntddchgr._CHANGER_SEND_VOLUME_TAG_INFORMATION
title: _CHANGER_SEND_VOLUME_TAG_INFORMATION (ntddchgr.h)
description: This structure is passed to the ChangerQueryVolumeTags routine and is used to specify a search criterion for retrieving changer elements.
old-location: storage\changer_send_volume_tag_information.htm
tech.root: storage
ms.assetid: cfe0673c-1dcb-4c4e-9ec4-8d9f27919c85
ms.date: 03/29/2018
keywords: ["_CHANGER_SEND_VOLUME_TAG_INFORMATION structure"]
ms.keywords: "*PCHANGER_SEND_VOLUME_TAG_INFORMATION, CHANGER_SEND_VOLUME_TAG_INFORMATION, CHANGER_SEND_VOLUME_TAG_INFORMATION structure [Storage Devices], PCHANGER_SEND_VOLUME_TAG_INFORMATION, PCHANGER_SEND_VOLUME_TAG_INFORMATION structure pointer [Storage Devices], _CHANGER_SEND_VOLUME_TAG_INFORMATION, ntddchgr/CHANGER_SEND_VOLUME_TAG_INFORMATION, ntddchgr/PCHANGER_SEND_VOLUME_TAG_INFORMATION, storage.changer_send_volume_tag_information, structs-changer_3f8d7f13-bf38-41fe-aa74-bbd9083bbbb6.xml"
f1_keywords:
 - "ntddchgr/CHANGER_SEND_VOLUME_TAG_INFORMATION"
 - "CHANGER_SEND_VOLUME_TAG_INFORMATION"
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
- CHANGER_SEND_VOLUME_TAG_INFORMATION
targetos: Windows
req.typenames: CHANGER_SEND_VOLUME_TAG_INFORMATION, *PCHANGER_SEND_VOLUME_TAG_INFORMATION
---

# _CHANGER_SEND_VOLUME_TAG_INFORMATION structure


## -description


This structure is passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a> routine and is used to specify a search criterion for retrieving changer elements. 


## -struct-fields




### -field StartingElement

Describes the first element of the range to search for or to set in a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>. 


### -field ActionCode

Indicates the operation to perform. The <b>Features0</b> member of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> indicates whether the changer supports a particular category of operation:

<ul>
<li>
Translate operations, also known as "searching operations", request that the target device search its volume tag information for elements that match the template passed to the device. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_SEARCH.

</li>
<li>
Assert operations define volume tag information for a single element. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_ASSERT.

</li>
<li>
Replace operations define volume tag information for a single element, overwriting any information previously defined. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_REPLACE. 

</li>
<li>
Undefined operations clear previously defined volume tag information for a single element. Valid only if <b>Features0</b> is set to CHANGER_VOLUME_UNDEFINE. 

</li>
</ul>

### -field VolumeIDTemplate

Specifies the template to be used by the device to search for volume IDs. For a translate operation, the template can include the wildcard characters, asterisk (*) and question mark (?), to search for volumes that match the template. For other operations, the template specifies a single volume. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_read_element_address_info">READ_ELEMENT_ADDRESS_INFO</a>
 

 

