---
UID: NS:ks.__unnamed_struct_29
title: KSDATAFORMAT (ks.h)
description: The KSDATAFORMAT structure is a variable-length structure that describes a data format.
old-location: stream\ksdataformat.htm
tech.root: stream
ms.assetid: e39a59f4-6ec2-402d-8f8e-12324d6cbfa8
ms.date: 04/23/2018
ms.keywords: "*PKSDATAFORMAT, *PKSDATARANGE, KSDATAFORMAT, KSDATAFORMAT structure [Streaming Media Devices], KSDATARANGE, KSDATARANGE structure [Streaming Media Devices], PKSDATAFORMAT, PKSDATAFORMAT structure pointer [Streaming Media Devices], PKSDATARANGE, PKSDATARANGE structure pointer [Streaming Media Devices], ks-struct_787a73ee-98dd-4e97-b7ea-2ed38ff564c7.xml, ks/KSDATAFORMAT, ks/KSDATARANGE, ks/PKSDATAFORMAT, ks/PKSDATARANGE, stream.ksdataformat"
ms.topic: struct
f1_keywords:
 - "ks/KSDATAFORMAT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ks.h
api_name:
- KSDATAFORMAT
product:
- Windows
targetos: Windows
req.typenames: KSDATAFORMAT, *PKSDATAFORMAT, KSDATARANGE, *PKSDATARANGE
---

# KSDATAFORMAT structure


## -description


The KSDATAFORMAT structure is a variable-length structure that describes a data format.


## -struct-fields




### -field FormatSize

Specifies the size, in bytes, of the KSDATAFORMAT structure. This must be at least <b>sizeof</b>(KSDATAFORMAT), but can be larger for specific settings of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b>. See the descriptions for these members for more information. 


### -field Flags

Set Flags to KSDATAFORMAT_ATTRIBUTES (0x2) to indicate that the KSDATAFORMAT is followed in memory by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item">KSMULTIPLE_ITEM</a> of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute">KSATTRIBUTE</a> structures.


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

For a list of <b>MajorFormat</b>, <b>SubFormat</b>, and <b>Specifier</b> combinations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-categories">Stream Categories</a> and its subtopics.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/stream/stream-categories">Stream Categories</a>
 

 

