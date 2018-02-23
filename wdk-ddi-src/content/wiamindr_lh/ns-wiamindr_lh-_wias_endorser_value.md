---
UID: NS:wiamindr_lh._WIAS_ENDORSER_VALUE
title: "_WIAS_ENDORSER_VALUE"
author: windows-driver-content
description: The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.
old-location: image\wias_endorser_value.htm
old-project: image
ms.assetid: 54395899-c35d-4251-9e9d-ec2128b28c67
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: WIAS_ENDORSER_VALUE, _WIAS_ENDORSER_VALUE, WIAS_ENDORSER_VALUE structure [Imaging Devices], wiastrct_b6e376e1-ecfd-4988-b752-3d81755cf990.xml, wiamindr_lh/WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE, wiamindr_lh/PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE, PWIAS_ENDORSER_VALUE structure pointer [Imaging Devices], image.wias_endorser_value
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
-	WIAS_ENDORSER_VALUE
product: Windows
targetos: Windows
req.typenames: WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE
req.product: Windows 10 or later.
---

# _WIAS_ENDORSER_VALUE structure


## -description


The WIAS_ENDORSER_VALUE structure stores token/value pairs for endorser strings.


## -syntax


````
typedef struct _WIAS_ENDORSER_VALUE {
  LPWSTR wszTokenName;
  LPWSTR wszValue;
} WIAS_ENDORSER_VALUE, *PWIAS_ENDORSER_VALUE;
````


## -struct-fields




### -field wszTokenName

Specifies a string value that represents the token name. Endorser token names begin and end with the $ character (for example, L"$MY_TOKEN_NAME$").


### -field wszValue

Specifies the value with which to replace the token.


## -remarks



This structure is used indirectly by the <a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a> function. One of the parameters of this function is a <a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_info.md">WIAS_ENDORSER_INFO</a> structure, which has a WIAS_ENDORSER_VALUE structure as one of its members.




## -see-also

<a href="..\wiamdef\nf-wiamdef-wiasparseendorserstring.md">wiasParseEndorserString</a>



<a href="..\wiamindr_lh\ns-wiamindr_lh-_wias_endorser_info.md">WIAS_ENDORSER_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20WIAS_ENDORSER_VALUE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

