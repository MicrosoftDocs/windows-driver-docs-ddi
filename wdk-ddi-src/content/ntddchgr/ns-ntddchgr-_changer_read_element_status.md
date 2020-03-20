---
UID: NS:ntddchgr._CHANGER_READ_ELEMENT_STATUS
title: _CHANGER_READ_ELEMENT_STATUS (ntddchgr.h)
description: The CHANGER_READ_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_GET_ELEMENT_STATUS request to retrieve the status of all elements or the status of a specified number of elements of a particular type.
old-location: storage\changer_read_element_status.htm
tech.root: storage
ms.assetid: 3e80790c-72b9-4e26-a767-a25e6425118e
ms.date: 03/29/2018
keywords: ["_CHANGER_READ_ELEMENT_STATUS structure"]
ms.keywords: "*PCHANGER_READ_ELEMENT_STATUS, CHANGER_READ_ELEMENT_STATUS, CHANGER_READ_ELEMENT_STATUS structure [Storage Devices], PCHANGER_READ_ELEMENT_STATUS, PCHANGER_READ_ELEMENT_STATUS structure pointer [Storage Devices], _CHANGER_READ_ELEMENT_STATUS, ntddchgr/CHANGER_READ_ELEMENT_STATUS, ntddchgr/PCHANGER_READ_ELEMENT_STATUS, storage.changer_read_element_status, structs-changer_bbb217cb-b38d-4d81-941f-ac1d78d0c584.xml"
f1_keywords:
 - "ntddchgr/CHANGER_READ_ELEMENT_STATUS"
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
- CHANGER_READ_ELEMENT_STATUS
product:
- Windows
targetos: Windows
req.typenames: CHANGER_READ_ELEMENT_STATUS, *PCHANGER_READ_ELEMENT_STATUS
---

# _CHANGER_READ_ELEMENT_STATUS structure


## -description


The CHANGER_READ_ELEMENT_STATUS structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a> request to retrieve the status of all elements or the status of a specified number of elements of a particular type. 


## -struct-fields




### -field ElementList

Specifies the element type and the number of elements of that type for which to report status in a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_list">CHANGER_ELEMENT_LIST</a>. This member contains a list of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>. The <b>ElementType</b> member of each CHANGER_ELEMENT structure in this list can be assigned a value of <b>ChangerDrive</b>, <b>ChangerSlot</b>, <b>ChangerTransport</b>, <b>ChangerIEPort</b>, or <b>AllElements</b>. 


### -field VolumeTagInfo

Indicates, when <b>TRUE</b>, that volume tag information should be reported in addition to element status. When <b>FALSE</b>, it indicates that only element status should be reported. A volume tag can be a bar code or an application-defined value assigned using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerqueryvolumetags">ChangerQueryVolumeTags</a>. This member is applicable only if either CHANGER_BAR_CODE_SCANNER_INSTALLED or CHANGER_VOLUME_IDENTIFICATION is set in the <b>Features0</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_list">CHANGER_ELEMENT_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_get_element_status">IOCTL_CHANGER_GET_ELEMENT_STATUS</a>
 

 

