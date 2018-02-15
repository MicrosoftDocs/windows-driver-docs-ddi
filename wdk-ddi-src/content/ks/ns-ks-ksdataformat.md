---
UID: NS:ks.KSDATAFORMAT
title: KSDATAFORMAT
author: windows-driver-content
description: The KSDATAFORMAT structure is a variable-length structure that describes a data format.
old-location: stream\ksdataformat.htm
old-project: stream
ms.assetid: e39a59f4-6ec2-402d-8f8e-12324d6cbfa8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: "*PKSDATARANGE, PKSDATAFORMAT, ks-struct_787a73ee-98dd-4e97-b7ea-2ed38ff564c7.xml, ks/PKSDATARANGE, ks/KSDATARANGE, PKSDATAFORMAT structure pointer [Streaming Media Devices], PKSDATARANGE, PKSDATARANGE structure pointer [Streaming Media Devices], ks/KSDATAFORMAT, KSDATAFORMAT structure [Streaming Media Devices], KSDATAFORMAT, *PKSDATAFORMAT, stream.ksdataformat, KSDATARANGE structure [Streaming Media Devices], KSDATARANGE, ks/PKSDATAFORMAT"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	KSDATAFORMAT
product: Windows
targetos: Windows
req.typenames: "*PKSDATAFORMAT, KSDATARANGE, *PKSDATARANGE, KSDATAFORMAT"
---

# KSDATAFORMAT structure


## -description


The KSDATAFORMAT structure is a variable-length structure that describes a data format.


## -syntax


````
typedef struct {
  ULONG FormatSize;
  ULONG Flags;
  ULONG SampleSize;
  ULONG Reserved;
  GUID  MajorFormat;
  GUID  SubFormat;
  GUID  Specifier;
} KSDATAFORMAT, *PKSDATAFORMAT, KSDATARANGE, *PKSDATARANGE;
````


## -struct-fields




### -field FormatSize

Specifies the size, in bytes, of the KSDATAFORMAT structure. This must be at least <b>sizeof</b>(KSDATAFORMAT), but can be larger for specific settings of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b>. See the descriptions for these members for more information. 


### -field Flags

Set Flags to KSDATAFORMAT_ATTRIBUTES (0x2) to indicate that the KSDATAFORMAT is followed in memory by a <a href="..\ks\ns-ks-ksmultiple_item.md">KSMULTIPLE_ITEM</a> of <a href="..\ks\ns-ks-ksattribute.md">KSATTRIBUTE</a> structures.


### -field SampleSize

Specifies the sample size of the data, for fixed sample sizes, or zero, if the format has a variable sample size.


### -field Reserved

Reserved for system use. Drivers must set this member to zero.


### -field MajorFormat

Specifies the general format type. The data formats that are currently supported can be found in the KSDATAFORMAT_TYPE_XXX symbolic constants in the <i>ksmedia.h</i> header file that is included in the Windows Driver Kit (WDK). A data stream that has no particular format should use KSDATAFORMAT_TYPE_STREAM (defined in <i>ks.h</i>) as the value for its <b>MajorFormat</b>. For more information about this member, see <b>Remarks</b>.


### -field SubFormat

Specifies the subformat of a general format type. The data subformats that are currently supported can be found in the KSDATAFORMAT_SUBTYPE_XXX symbolic constants in the <i>ksmedia.h</i> header file that is included in the WDK. Major formats that do not support subformats should use the KSDATAFORMAT_SUBTYPE_NONE value for this member. For more information about this member, see <b>Remarks</b>.


### -field Specifier

Specifies additional data format type information for a specific setting of <b>MajorFormat</b> and <b>SubFormat</b>. 
	  The significance of this field is determined by the major format (and subformat, if the major format supports subformats). For example, <b>Specifier</b> can represent a particular encoding of a subformat, or it can be used to specify what type of data structure follows KSDATAFORMAT in memory.

The following specifiers (defined in <i>ks.h</i>) are of general use:





#### KSDATAFORMAT_SPECIFIER_NONE

Stands for no specifier. Used for formats that do not support specifiers.



#### KSDATAFORMAT_SPECIFIER_FILENAME

Indicates that a null-terminated Unicode string immediately follows the KSDATAFORMAT structure in memory.  



#### KSDATAFORMAT_SPECIFIER_FILEHANDLE

Indicates that a file handle immediately follows KSDATAFORMAT in memory.  


## -remarks



At the minimum, a data format is specified by the <b>MajorFormat</b>, the <b>SubFormat</b>, and the <b>Specifier</b> members. A family of similar data formats can share the same values for <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b>. In that case, the specific data format is distinguished by additional data that follows the <b>Specifier</b> member in memory.

For a list of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b> combinations, see <a href="https://msdn.microsoft.com/dc2af282-4976-42d8-b07b-13b2a6dfb7d5">Stream Categories</a> and its subtopics.




## -see-also

<a href="https://msdn.microsoft.com/dc2af282-4976-42d8-b07b-13b2a6dfb7d5">Stream Categories</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSDATAFORMAT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

