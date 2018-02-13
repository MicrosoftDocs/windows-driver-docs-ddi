---
UID: NS:hidpddi._HIDP_GETCOLDESC_DBG
title: "_HIDP_GETCOLDESC_DBG"
author: windows-driver-content
description: Contains the error code indicating the failure in parsing the report descriptor. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_getcoldesc_dbg.htm
old-project: hid
ms.assetid: 65EEEDED-14FE-4275-9314-276E544427DE
ms.author: windowsdriverdev
ms.date: 12/21/2017
ms.keywords: hidpddi/HIDP_GETCOLDESC_DBG, PHIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG structure [Human Input Devices], hid.hidp_getcoldesc_dbg, _HIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG, PHIDP_GETCOLDESC_DBG structure pointer [Human Input Devices], hidpddi/PHIDP_GETCOLDESC_DBG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Hidpddi.h
apiname:
-	HIDP_GETCOLDESC_DBG
product: Windows
targetos: Windows
req.typenames: "*PHIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG"
---

# _HIDP_GETCOLDESC_DBG structure


## -description


Contains the error code indicating the failure in parsing the report 
                                      descriptor. This structure is used in the <a href="..\hidpddi\nf-hidpddi-hidp_getcollectiondescription.md">HidP_GetCollectionDescription</a> call.


## -syntax


````
typedef struct _HIDP_GETCOLDESC_DBG {
  ULONG BreakOffset;
  ULONG ErrorCode;
  ULONG Args[6];
} HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG;
````


## -struct-fields




### -field BreakOffset

The byte offset in the report descriptor where the parsing error occurred.


### -field ErrorCode

Indicates the parsing error, if it’s not HIDP_GETCOLDESC_SUCCESS.

All possible values are defined in hidpddi.h, from HIDP_GETCOLDESC_SUCCESS to the end  of the file.



### -field Args

Error-specific arguments. These are described as comments in the possible values for <b>ErrorCode</b> in hidpddi.h.


## -see-also

<a href="..\hidpddi\nf-hidpddi-hidp_getcollectiondescription.md">HidP_GetCollectionDescription</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [hid\hid]:%20HIDP_GETCOLDESC_DBG structure%20 RELEASE:%20(12/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

