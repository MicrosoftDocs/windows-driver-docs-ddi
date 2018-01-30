---
UID: NS:ntddk._WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
title: "_WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS"
author: windows-driver-content
description: The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union describes which members of a WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contain valid data.
old-location: whea\whea_error_record_section_descriptor_validbits.htm
old-project: whea
ms.assetid: 7d1f192b-75fe-4ee0-b162-401230299562
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, whea.whea_error_record_section_descriptor_validbits, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union [WHEA Drivers and Applications], _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, ntddk/WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union pointer [WHEA Drivers and Applications], whearef_0e13e9d6-57cb-44bd-825e-d9cab5c138c8.xml, ntddk/PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS
product: Windows
targetos: Windows
req.typenames: "*PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS"
---

# _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS structure


## -description


The WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure contain valid data.


## -syntax


````
typedef union _WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS {
  struct {
    UCHAR FRUId  :1;
    UCHAR FRUText  :1;
    UCHAR Reserved  :6;
  };
  UCHAR  AsUCHAR;
} WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS, *PWHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.FRUId

 


### -field DUMMYSTRUCTNAME.FRUText

 


### -field DUMMYSTRUCTNAME.Reserved

 


### -field AsUCHAR

A UCHAR representation of the contents of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union.


#### - FRUId

A single bit that indicates that the <b>FRUId</b> member of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contains valid data.


#### - FRUText

A single bit that indicates that the <b>FRUText</b> member of the WHEA_ERROR_RECORD_SECTION_DESCRIPTOR structure contains valid data.


#### - Reserved

Reserved for system use.


## -remarks


A WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structure.



## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_ERROR_RECORD_SECTION_DESCRIPTOR_VALIDBITS union%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

