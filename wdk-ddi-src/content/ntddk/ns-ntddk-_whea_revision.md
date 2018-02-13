---
UID: NS:ntddk._WHEA_REVISION
title: "_WHEA_REVISION"
author: windows-driver-content
description: The WHEA_REVISION union describes the revision of the error record data structures.
old-location: whea\whea_revision.htm
old-project: whea
ms.assetid: 4258f223-353a-4b6e-a93c-5742e5c1668b
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: WHEA_REVISION union [WHEA Drivers and Applications], _WHEA_REVISION, WHEA_REVISION, PWHEA_REVISION, whea.whea_revision, ntddk/WHEA_REVISION, whearef_0572aecb-765a-4118-8df0-7b34922e79d9.xml, ntddk/PWHEA_REVISION, PWHEA_REVISION union pointer [WHEA Drivers and Applications], *PWHEA_REVISION
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
-	WHEA_REVISION
product: Windows
targetos: Windows
req.typenames: "*PWHEA_REVISION, WHEA_REVISION"
---

# _WHEA_REVISION structure


## -description


The WHEA_REVISION union describes the revision of the error record data structures.


## -syntax


````
typedef union _WHEA_REVISION {
  struct {
    UCHAR MinorRevision;
    UCHAR MajorRevision;
  };
  USHORT AsUSHORT;
} WHEA_REVISION, *PWHEA_REVISION;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field DUMMYSTRUCTNAME.MinorRevision

The minor revision number.


### -field DUMMYSTRUCTNAME.MajorRevision

The major revision number.


### -field AsUSHORT

A USHORT representation of the contents of the WHEA_REVISION union.


## -remarks



A WHEA_REVISION union is contained within the <a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a> and the <a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a> structures.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_error_record_section_descriptor.md">WHEA_ERROR_RECORD_SECTION_DESCRIPTOR</a>



<a href="..\ntddk\ns-ntddk-_whea_error_record_header.md">WHEA_ERROR_RECORD_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_REVISION union%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

