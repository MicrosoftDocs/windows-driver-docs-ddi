---
UID: NS:wiamindr_lh._WIAS_ENDORSER_INFO
title: _WIAS_ENDORSER_INFO
author: windows-driver-content
description: The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs.
old-location: image\wias_endorser_info.htm
old-project: image
ms.assetid: 4874ddab-5443-4e03-8f49-493682dabac1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: WIAS_ENDORSER_INFO, image.wias_endorser_info, wiamindr_lh/PWIAS_ENDORSER_INFO, WIAS_ENDORSER_INFO structure [Imaging Devices], _WIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO, PWIAS_ENDORSER_INFO structure pointer [Imaging Devices], wiamindr_lh/WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO, wiastrct_de79ab57-ad51-4bf0-90cb-51bd1a8352bd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Me and in Windows XP and later versions of the Windows operating systems.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	wiamindr_lh.h
apiname: 
-	WIAS_ENDORSER_INFO
product: Windows
targetos: Windows
req.typenames: WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO
req.product: Windows 10 or later.
---

# _WIAS_ENDORSER_INFO structure


## -description


The WIAS_ENDORSER_INFO structure holds custom endorser token/value pairs.


## -syntax


````
typedef struct _WIAS_ENDORSER_INFO {
  ULONG               ulPageCount;
  ULONG               ulNumEndorserValues;
  WIAS_ENDORSER_VALUE *pEndorserValues;
} WIAS_ENDORSER_INFO, *PWIAS_ENDORSER_INFO;
````


## -struct-fields




### -field ulPageCount

Specifies the value that will replace the $PAGE_COUNT$ token, provided that the endorser string contains that token.


### -field ulNumEndorserValues

Specifies the number of token/value pairs. This member will be 0 if there are no custom token/value pairs.


### -field pEndorserValues

Points to an array of <a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_value.md">WIAS_ENDORSER_VALUE</a> structures, holding custom token/value pairs. If the value of the <b>ulNumEndorserValues</b> member is 0, this member should be <b>NULL</b>.


## -remarks


Currently, <a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a> recognizes three endorser tokens: $DATE$, $TIME$, $PAGE_COUNT$, $DAY$, $MONTH$, and $YEAR$. (See <i>wiamdef.h</i>.) Any other tokens and their values must be specified in the <b>pEndorserValues</b> member of this structure.



## -see-also

<a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_value.md">WIAS_ENDORSER_VALUE</a>

<a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_ENDORSER_INFO structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

