---
UID: NS:ntddchgr._CHANGER_ELEMENT_LIST
title: _CHANGER_ELEMENT_LIST (ntddchgr.h)
description: The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type.
old-location: storage\changer_element_list.htm
tech.root: storage
ms.assetid: 6e85eaa7-d622-4b05-9efd-c1b6b7789c03
ms.date: 03/29/2018
keywords: ["CHANGER_ELEMENT_LIST structure"]
ms.keywords: "*PCHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST, CHANGER_ELEMENT_LIST structure [Storage Devices], PCHANGER_ELEMENT_LIST, PCHANGER_ELEMENT_LIST structure pointer [Storage Devices], _CHANGER_ELEMENT_LIST, ntddchgr/CHANGER_ELEMENT_LIST, ntddchgr/PCHANGER_ELEMENT_LIST, storage.changer_element_list, structs-changer_e1782d96-458d-49a5-9885-c853d835ba0a.xml"
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
req.typenames: CHANGER_ELEMENT_LIST, *PCHANGER_ELEMENT_LIST
f1_keywords:
 - _CHANGER_ELEMENT_LIST
 - ntddchgr/_CHANGER_ELEMENT_LIST
 - PCHANGER_ELEMENT_LIST
 - ntddchgr/PCHANGER_ELEMENT_LIST
 - CHANGER_ELEMENT_LIST
 - ntddchgr/CHANGER_ELEMENT_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddchgr.h
api_name:
 - CHANGER_ELEMENT_LIST
---

# _CHANGER_ELEMENT_LIST structure


## -description

The CHANGER_ELEMENT_LIST structure indicates a range of elements of a single type.

## -struct-fields

### -field Element

Describes the first element of type <a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a> in a range <b>NumberOfElements</b> long.

### -field NumberOfElements

Specifies the number of elements in the range.

## -remarks

A changer class driver uses CHANGER_ELEMENT_LIST to indicate a range of elements of a single type, typically for an operation such as getting or initializing the status of multiple elements.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddchgr/ns-ntddchgr-_changer_element">CHANGER_ELEMENT</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changergetelementstatus">ChangerGetElementStatus</a>



<a href="/windows-hardware/drivers/ddi/mcd/nf-mcd-changerinitializeelementstatus">ChangerInitializeElementStatus</a>