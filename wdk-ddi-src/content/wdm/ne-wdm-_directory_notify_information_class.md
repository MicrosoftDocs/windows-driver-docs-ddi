---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
tech.root: ifsk
title: DIRECTORY_NOTIFY_INFORMATION_CLASS
ms.date: 02/05/2024
targetos: Windows
description: Learn more about the DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration.
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

A **DIRECTORY_NOTIFY_INFORMATION_CLASS** value specifies which structure to use to query or set information for files in a directory.

## -enum-fields

### -field DirectoryNotifyInformation

Use a [**FILE_NOTIFY_INFORMATION**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-file_notify_information) structure.

### -field DirectoryNotifyExtendedInformation

Use a [**FILE_NOTIFY_EXTENDED_INFORMATION**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-file_notify_extended_information) structure.

### -field DirectoryNotifyFullInformation

Use a [**FILE_NOTIFY_FULL_INFORMATION**](/windows-hardware/drivers/ddi/ntifs/ns-ntifs-file_notify_full_information) structure. Supported starting in Windows 11, version 22H2.

### -field DirectoryNotifyMaximumInformation

The maximum value for this enumeration.

## -see-also

[**IRP_MJ_DIRECTORY_CONTROL**](/windows-hardware/drivers/ifs/irp-mj-directory-control)

