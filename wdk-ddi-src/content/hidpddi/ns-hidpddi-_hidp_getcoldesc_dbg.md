---
UID: NS:hidpddi._HIDP_GETCOLDESC_DBG
title: _HIDP_GETCOLDESC_DBG (hidpddi.h)
description: Contains the error code indicating the failure in parsing the report descriptor. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_getcoldesc_dbg.htm
tech.root: hid
ms.assetid: 65EEEDED-14FE-4275-9314-276E544427DE
ms.date: 04/30/2018
keywords: ["HIDP_GETCOLDESC_DBG structure"]
ms.keywords: "*PHIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG structure [Human Input Devices], PHIDP_GETCOLDESC_DBG, PHIDP_GETCOLDESC_DBG structure pointer [Human Input Devices], _HIDP_GETCOLDESC_DBG, hid.hidp_getcoldesc_dbg, hidpddi/HIDP_GETCOLDESC_DBG, hidpddi/PHIDP_GETCOLDESC_DBG"
f1_keywords:
 - "hidpddi/HIDP_GETCOLDESC_DBG"
 - "HIDP_GETCOLDESC_DBG"
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
- Hidpddi.h
api_name:
- HIDP_GETCOLDESC_DBG
targetos: Windows
req.typenames: HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG
---

# _HIDP_GETCOLDESC_DBG structure


## -description


Contains the error code indicating the failure in parsing the report 
                                      descriptor. This structure is used in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpddi/nf-hidpddi-hidp_getcollectiondescription">HidP_GetCollectionDescription</a> call.


## -struct-fields




### -field BreakOffset

The byte offset in the report descriptor where the parsing error occurred.


### -field ErrorCode

Indicates the parsing error, if it’s not HIDP_GETCOLDESC_SUCCESS.

All possible values are defined in hidpddi.h, from HIDP_GETCOLDESC_SUCCESS to the end  of the file.



### -field Args

Error-specific arguments. These are described as comments in the possible values for <b>ErrorCode</b> in hidpddi.h.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/hidpddi/nf-hidpddi-hidp_getcollectiondescription">HidP_GetCollectionDescription</a>
 

 

