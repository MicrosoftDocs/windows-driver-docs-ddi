---
UID: NS:winspool._BIDI_DATA
title: "_BIDI_DATA"
author: windows-driver-content
description: The BIDI_DATA structure is used to store the values of a bidi schema.
old-location: print\bidi_data.htm
old-project: print
ms.assetid: 9e0f3044-01c0-4dec-b34c-0f33ccfe3300
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPBIDI_DATA, *PBIDI_DATA, BIDI_DATA, BIDI_DATA structure [Print Devices], LPBIDI_DATA, LPBIDI_DATA structure pointer [Print Devices], PBIDI_DATA, PBIDI_DATA structure pointer [Print Devices], _BIDI_DATA, print.bidi_data, spoolfnc_6e6c0bc2-88f6-43ab-8183-42ee1a91e593.xml, winspool/BIDI_DATA, winspool/LPBIDI_DATA, winspool/PBIDI_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winspool.h
req.include-header: Winspool.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later.
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
-	winspool.h
api_name:
-	BIDI_DATA
product: Windows
targetos: Windows
req.typenames: BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA
req.product: Windows 10 or later.
---

# _BIDI_DATA structure


## -description


The BIDI_DATA structure is used to store the values of a bidi schema.


## -syntax


````
typedef struct _BIDI_DATA {
  DWORD dwBidiType;
  union {
    BOOL             bData;
    LONG             iData;
    LPWSTR           sData;
    FLOAT            fData;
    BINARY_CONTAINER biData;
  } u;
} BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA;
````


## -struct-fields




### -field dwBidiType

Specifies the type of data in a bidi request as one of the values listed in the <a href="..\winspool\ne-winspool-bidi_type.md">BIDI_TYPE</a> enumeration. The value of this member determines which one of the following five union members is valid.


### -field u



#### bData

Specifies the Boolean value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BOOL, one of the BIDI_TYPE enumerators.



#### iData

Specifies the integer value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_INT, one of the BIDI_TYPE enumerators.



#### sData

Pointer to a memory location at which the first byte of the string is stored. This member is valid only if the value of <b>dwBidiType</b> is BIDI_STRING or BIDI_TEXT, two of the BIDI_TYPE enumerators.



#### fData

Specifies the floating-point value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_FLOAT, one of the BIDI_TYPE enumerators.



#### biData

Specifies a <a href="..\winspool\ns-winspool-_binary_container.md">BINARY_CONTAINER</a> structure that holds the binary data. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BLOB, one of the BIDI_TYPE enumerators.


## -remarks



The <a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a> and <a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a> structures each have a member of this type, which holds the bidi data for the request or response.




## -see-also

<a href="..\winspool\ns-winspool-_bidi_request_data.md">BIDI_REQUEST_DATA</a>



<a href="..\winspool\ns-winspool-_binary_container.md">BINARY_CONTAINER</a>



<a href="..\winspool\ns-winspool-_bidi_response_data.md">BIDI_RESPONSE_DATA</a>



<a href="..\winspool\ne-winspool-bidi_type.md">BIDI_TYPE</a>



 

 


