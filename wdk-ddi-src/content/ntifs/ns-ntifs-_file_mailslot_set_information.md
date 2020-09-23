---
UID: NS:ntifs._FILE_MAILSLOT_SET_INFORMATION
title: _FILE_MAILSLOT_SET_INFORMATION (ntifs.h)
description: The FILE_MAILSLOT_SET_INFORMATION structure is used to set a value on a mailslot.
old-location: ifsk\file_mailslot_set_information.htm
tech.root: ifsk
ms.assetid: 65104303-5041-45e7-bd59-bb78dde1dffd
ms.date: 04/16/2018
keywords: ["FILE_MAILSLOT_SET_INFORMATION structure"]
ms.keywords: "*PFILE_MAILSLOT_SET_INFORMATION, FILE_MAILSLOT_SET_INFORMATION, FILE_MAILSLOT_SET_INFORMATION structure [Installable File System Drivers], PFILE_MAILSLOT_SET_INFORMATION, PFILE_MAILSLOT_SET_INFORMATION structure pointer [Installable File System Drivers], _FILE_MAILSLOT_SET_INFORMATION, ifsk.file_mailslot_set_information, ntifs/FILE_MAILSLOT_SET_INFORMATION, ntifs/PFILE_MAILSLOT_SET_INFORMATION"
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating system.
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
req.typenames: FILE_MAILSLOT_SET_INFORMATION, *PFILE_MAILSLOT_SET_INFORMATION
f1_keywords:
 - _FILE_MAILSLOT_SET_INFORMATION
 - ntifs/_FILE_MAILSLOT_SET_INFORMATION
 - PFILE_MAILSLOT_SET_INFORMATION
 - ntifs/PFILE_MAILSLOT_SET_INFORMATION
 - FILE_MAILSLOT_SET_INFORMATION
 - ntifs/FILE_MAILSLOT_SET_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - FILE_MAILSLOT_SET_INFORMATION
---

# _FILE_MAILSLOT_SET_INFORMATION structure


## -description

The <b>FILE_MAILSLOT_SET_INFORMATION</b> structure is used to set a value on a   mailslot.

## -struct-fields

### -field ReadTimeout

The time, in milliseconds, that a read operation can wait for a message to be written to the mailslot before a time-out occurs. A value of –1 requests that the read wait forever for a message without timing out. A value of 0 requests that the read not wait and return immediately whether a pending message is available to be read or not.

## -remarks

For more information, see <a href="/windows/desktop/ipc/mailslots">Mailslots</a>.