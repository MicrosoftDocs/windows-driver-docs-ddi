---
UID: NS:winspool._BIDI_DATA
title: "_BIDI_DATA"
description: The BIDI_DATA structure is used to store the values of a bidi schema.
old-location: print\bidi_data.htm
tech.root: print
ms.assetid: 9e0f3044-01c0-4dec-b34c-0f33ccfe3300
ms.date: 04/20/2018
ms.keywords: "*LPBIDI_DATA, *PBIDI_DATA, BIDI_DATA, BIDI_DATA structure [Print Devices], LPBIDI_DATA, LPBIDI_DATA structure pointer [Print Devices], PBIDI_DATA, PBIDI_DATA structure pointer [Print Devices], _BIDI_DATA, print.bidi_data, spoolfnc_6e6c0bc2-88f6-43ab-8183-42ee1a91e593.xml, winspool/BIDI_DATA, winspool/LPBIDI_DATA, winspool/PBIDI_DATA"
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
product:
- Windows
targetos: Windows
req.typenames: BIDI_DATA, *PBIDI_DATA, *LPBIDI_DATA
---

# _BIDI_DATA structure


## -description


The BIDI_DATA structure is used to store the values of a bidi schema.


## -struct-fields




### -field dwBidiType

Specifies the type of data in a bidi request as one of the values listed in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545211">BIDI_TYPE</a> enumeration. The value of this member determines which one of the following five union members is valid.


### -field u


### -field u.bData

Specifies the Boolean value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BOOL, one of the BIDI_TYPE enumerators.


### -field u.iData

Specifies the integer value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_INT, one of the BIDI_TYPE enumerators.


### -field u.sData

Pointer to a memory location at which the first byte of the string is stored. This member is valid only if the value of <b>dwBidiType</b> is BIDI_STRING or BIDI_TEXT, two of the BIDI_TYPE enumerators.


### -field u.fData

Specifies the floating-point value. This member is valid only if the value of <b>dwBidiType</b> is BIDI_FLOAT, one of the BIDI_TYPE enumerators.


### -field u.biData

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff545212">BINARY_CONTAINER</a> structure that holds the binary data. This member is valid only if the value of <b>dwBidiType</b> is BIDI_BLOB, one of the BIDI_TYPE enumerators.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545196">BIDI_REQUEST_DATA</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545204">BIDI_RESPONSE_DATA</a> structures each have a member of this type, which holds the bidi data for the request or response.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545196">BIDI_REQUEST_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545204">BIDI_RESPONSE_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545211">BIDI_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545212">BINARY_CONTAINER</a>
 

 

