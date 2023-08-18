---
UID: NS:ks.KSDATAFORMAT~r1
tech.root: stream
title: KSDATAFORMAT
ms.date: 08/08/2023
targetos: Windows
description: This topic describes the KSDATAFORMAT union.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ks.h
req.include-header: Ks.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: KSDATAFORMAT, *PKSDATAFORMAT, KSDATARANGE, *PKSDATARANGE
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSDATAFORMAT
 - PKSDATAFORMAT
f1_keywords:
 - KSDATAFORMAT
 - ks/KSDATAFORMAT
 - PKSDATAFORMAT
 - ks/PKSDATAFORMAT
dev_langs:
 - c++
helpviewer_keywords:
 - KSDATAFORMAT
---

## -description

This topic describes the **KSDATAFORMAT** union.

## -struct-fields

### -field FormatSize

Specifies the size, in bytes, of the **KSDATAFORMAT** union. This must be at least **sizeof**(**KSDATAFORMAT**), but can be larger for specific settings of **MajorFormat**, **SubFormat**, and **Specifier**. See the descriptions for these members for more information.

### -field Flags

Set Flags to KSDATAFORMAT_ATTRIBUTES (0x2) to indicate that the **KSDATAFORMAT** is followed in memory by a [**KSMULTIPLE_ITEM**](/windows-hardware/drivers/ddi/ks/ns-ks-ksmultiple_item) of [**KSATTRIBUTE**](/windows-hardware/drivers/ddi/ks/ns-ks-ksattribute) structures.

### -field SampleSize

Specifies the sample size of the data, for fixed sample sizes, or zero, if the format has a variable sample size.

### -field Reserved

Reserved for system use. Drivers must set this member to zero.

### -field MajorFormat

Specifies the general format type. The data formats that are currently supported can be found in the KSDATAFORMAT_TYPE_XXX symbolic constants in the *ksmedia.h* header file that is included in the Windows Driver Kit (WDK). A data stream that has no particular format should use KSDATAFORMAT_TYPE_STREAM (defined in *ks.h*) as the value for its **MajorFormat**. For more information about this member, see **Remarks**.

### -field SubFormat

Specifies the subformat of a general format type. The data subformats that are currently supported can be found in the KSDATAFORMAT_SUBTYPE_XXX symbolic constants in the *ksmedia.h* header file that is included in the WDK. Major formats that do not support subformats should use the KSDATAFORMAT_SUBTYPE_NONE value for this member. For more information about this member, see **Remarks**.

### -field Specifier

Specifies additional data format type information for a specific setting of **MajorFormat** and **SubFormat**.
      The significance of this field is determined by the major format (and subformat, if the major format supports subformats). For example, **Specifier** can represent a particular encoding of a subformat, or it can be used to specify what type of data structure follows **KSDATAFORMAT** in memory.

The following specifiers (defined in *ks.h*) are of general use:

#### KSDATAFORMAT_SPECIFIER_NONE

Stands for no specifier. Used for formats that do not support specifiers.

#### KSDATAFORMAT_SPECIFIER_FILENAME

Indicates that a null-terminated Unicode string immediately follows the **KSDATAFORMAT** union in memory.  

#### KSDATAFORMAT_SPECIFIER_FILEHANDLE

Indicates that a file handle immediately follows **KSDATAFORMAT** in memory.

### -field Alignment

Defines the **LONGLONG** member **Alignment**.

## -remarks

At the minimum, a data format is specified by the **MajorFormat**, the **SubFormat**, and the **Specifier** members. A family of similar data formats can share the same values for **MajorFormat**, **SubFormat**, and **Specifier**. In that case, the specific data format is distinguished by additional data that follows the **Specifier** member in memory.

For a list of **MajorFormat**, **SubFormat**, and **Specifier** combinations, see [Stream categories](/windows-hardware/drivers/stream/stream-categories) and its subtopics.

## -see-also

[Stream categories](/windows-hardware/drivers/stream/stream-categories)
