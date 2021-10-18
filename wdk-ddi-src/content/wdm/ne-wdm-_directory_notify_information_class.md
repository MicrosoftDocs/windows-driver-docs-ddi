---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
title: _DIRECTORY_NOTIFY_INFORMATION_CLASS (wdm.h)
description: A value that specifies which structure to use to query or set information for a files in a directory.
tech.root: ifsk
ms.date: 06/11/2021
keywords: ["DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration"]
ms.keywords: "*PDIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], DirectoryNotifyExtendedInformation, DirectoryNotifyInformation, _DIRECTORY_NOTIFY_INFORMATION_CLASS, ifsk._directory_notify_information_class, wdm/DIRECTORY_NOTIFY_INFORMATION_CLASS, wdm/DirectoryNotifyExtendedInformation, wdm/DirectoryNotifyInformation"
req.header: wdm.h
req.include-header:  Wdm.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.typenames: DIRECTORY_NOTIFY_INFORMATION_CLASS, *PDIRECTORY_NOTIFY_INFORMATION_CLASS
f1_keywords:
 - _DIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/_DIRECTORY_NOTIFY_INFORMATION_CLASS
 - PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - DIRECTORY_NOTIFY_INFORMATION_CLASS
 - wdm/DIRECTORY_NOTIFY_INFORMATION_CLASS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - _DIRECTORY_NOTIFY_INFORMATION_CLASS
 - PDIRECTORY_NOTIFY_INFORMATION_CLASS
 - DIRECTORY_NOTIFY_INFORMATION_CLASS
---

# _DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration

## -description

A value that specifies which structure to use to query or set information for a files in a directory.

## -enum-fields

### -field DirectoryNotifyInformation

A **FILE_NOTIFY_INFORMATION** structure.

### -field DirectoryNotifyExtendedInformation

A **FILE_NOTIFY_EXTENDED_INFORMATION** structure.
