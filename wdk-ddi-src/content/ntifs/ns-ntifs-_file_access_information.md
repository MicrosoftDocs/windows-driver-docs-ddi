---
UID: NS:ntifs._FILE_ACCESS_INFORMATION
title: _FILE_ACCESS_INFORMATION (ntifs.h)
description: The FILE_ACCESS_INFORMATION structure is used to query for or set the access rights of a file.
old-location: kernel\file_access_information.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["FILE_ACCESS_INFORMATION structure"]
ms.keywords: "*PFILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION, FILE_ACCESS_INFORMATION structure [Kernel-Mode Driver Architecture], PFILE_ACCESS_INFORMATION, PFILE_ACCESS_INFORMATION structure pointer [Kernel-Mode Driver Architecture], _FILE_ACCESS_INFORMATION, kernel.file_access_information, kstruct_b_3419b751-aa57-41e2-a51d-35bb5a6f38c8.xml, ntifs/FILE_ACCESS_INFORMATION, ntifs/PFILE_ACCESS_INFORMATION"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP
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
targetos: Windows
req.typenames: FILE_ACCESS_INFORMATION, *PFILE_ACCESS_INFORMATION
f1_keywords:
 - _FILE_ACCESS_INFORMATION
 - ntifs/_FILE_ACCESS_INFORMATION
 - PFILE_ACCESS_INFORMATION
 - ntifs/PFILE_ACCESS_INFORMATION
 - FILE_ACCESS_INFORMATION
 - ntifs/FILE_ACCESS_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _FILE_ACCESS_INFORMATION
 - PFILE_ACCESS_INFORMATION
 - FILE_ACCESS_INFORMATION
---

# _FILE_ACCESS_INFORMATION structure


## -description

The <b>FILE_ACCESS_INFORMATION</b> structure is used to query for or set the access rights of a file.

## -struct-fields

### -field AccessFlags

Flags that specify a set of access rights in the access mask of an access control entry. This member is a value of type <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>.

## -remarks

This structure is used by the <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a> routine.

The <i>AccessFlags</i> parameter is an access mask that encodes the user rights to a file object. An access mask can be used to encode the rights to an object that is assigned to a user or a user group, or to encode the requested access when a user opens an object. For more information, see <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntqueryinformationfile">ZwQueryInformationFile</a>

