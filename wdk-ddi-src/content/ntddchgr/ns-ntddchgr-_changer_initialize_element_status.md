---
UID: NS:ntddchgr._CHANGER_INITIALIZE_ELEMENT_STATUS
title: _CHANGER_INITIALIZE_ELEMENT_STATUS (ntddchgr.h)
description: The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS request to initialize the status of all elements or of a specified number of elements of a particular type.
old-location: storage\changer_initialize_element_status.htm
tech.root: storage
ms.assetid: fd26a97d-cbea-4ab4-b54e-1831d6e3a8ed
ms.date: 03/29/2018
keywords: ["_CHANGER_INITIALIZE_ELEMENT_STATUS structure"]
ms.keywords: "*PCHANGER_INITIALIZE_ELEMENT_STATUS, CHANGER_INITIALIZE_ELEMENT_STATUS, CHANGER_INITIALIZE_ELEMENT_STATUS structure [Storage Devices], PCHANGER_INITIALIZE_ELEMENT_STATUS, PCHANGER_INITIALIZE_ELEMENT_STATUS structure pointer [Storage Devices], _CHANGER_INITIALIZE_ELEMENT_STATUS, ntddchgr/CHANGER_INITIALIZE_ELEMENT_STATUS, ntddchgr/PCHANGER_INITIALIZE_ELEMENT_STATUS, storage.changer_initialize_element_status, structs-changer_94235bd7-09e6-47a1-b30c-0d5d12ca7917.xml"
f1_keywords:
 - "ntddchgr/CHANGER_INITIALIZE_ELEMENT_STATUS"
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
- CHANGER_INITIALIZE_ELEMENT_STATUS
product:
- Windows
targetos: Windows
req.typenames: CHANGER_INITIALIZE_ELEMENT_STATUS, *PCHANGER_INITIALIZE_ELEMENT_STATUS
---

# _CHANGER_INITIALIZE_ELEMENT_STATUS structure


## -description


The CHANGER_INITIALIZE_ELEMENT_STATUS structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_initialize_element_status">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a> request to initialize the status of all elements or of a specified number of elements of a particular type. 


## -struct-fields




### -field ElementList

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_list">CHANGER_ELEMENT_LIST</a> that specifies the element type and the number of elements. If the <b>Features0</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a> structure is set to CHANGER_INIT_ELEM_STAT_WITH_RANGE, the changer supports initializing a range of elements. In this case, the element type can be <b>ChangerTransport</b>, <b>ChangerSlot</b>, <b>ChangerDrive</b>, or <b>ChangerIEPort</b> and <b>ElementList</b> can specify a number of elements to initialize. Otherwise, the element type must be <b>AllElements</b> and the number of elements is ignored. 


### -field BarCodeScan

Instructs the changer driver, when <b>TRUE</b>, to initialize elements by scanning bar codes. When <b>FALSE</b>, the changer driver takes no action. This member is applicable only if the <b>Features0</b> member of GET_CHANGER_PARAMETERS is set to CHANGER_BAR_CODE_SCANNER_INSTALLED. If the changer has nonvolatile RAM, a bar code scan can serve as an optimization.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element_list">CHANGER_ELEMENT_LIST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitializeelementstatus">ChangerInitializeElementStatus</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_get_changer_parameters">GET_CHANGER_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddchgr/ni-ntddchgr-ioctl_changer_initialize_element_status">IOCTL_CHANGER_INITIALIZE_ELEMENT_STATUS</a>
 

 

