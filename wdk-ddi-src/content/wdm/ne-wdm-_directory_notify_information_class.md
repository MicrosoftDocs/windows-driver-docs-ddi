---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
tech.root: ifsk
title: DIRECTORY_NOTIFY_INFORMATION_CLASS
ms.date: 03/01/2022
targetos: Windows
description: A value that specifies which structure to use to query or set information for a files in a directory.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.target-type: Windows
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DIRECTORY_NOTIFY_INFORMATION_CLASS
 - PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - DIRECTORY_NOTIFY_INFORMATION_CLASS
f1_keywords:
 - _DIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/_DIRECTORY_NOTIFY_INFORMATION_CLASS
 - PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - DIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/DIRECTORY_NOTIFY_INFORMATION_CLASS
dev_langs:
 - c++
helpviewer_keywords:
 - _DIRECTORY_NOTIFY_INFORMATION_CLASS
---

## -description

A value that specifies which structure to use to query or set information for a files in a directory.

## -enum-fields

### -field DirectoryNotifyInformation

A **FILE_NOTIFY_INFORMATION** structure.

### -field DirectoryNotifyExtendedInformation

A **FILE_NOTIFY_EXTENDED_INFORMATION** structure.

### -field DirectoryNotifyFullInformation

A **FILE_NOTIFY_FULL_INFORMATION** structure.

## -remarks

## -see-also
