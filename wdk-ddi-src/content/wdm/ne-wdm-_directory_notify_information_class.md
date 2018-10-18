---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
title: "_DIRECTORY_NOTIFY_INFORMATION_CLASS"
author: windows-driver-content
description: A value that specifies which structure to use to query or set information for a files in a directory.
old-location: ifsk\_directory_notify_information_class.htm
tech.root: ifsk
ms.assetid: 77c2515b-f20a-47ac-9564-9eab009cf625
ms.date: 04/16/2018
ms.keywords: "*PDIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], DirectoryNotifyExtendedInformation, DirectoryNotifyInformation, _DIRECTORY_NOTIFY_INFORMATION_CLASS, ifsk._directory_notify_information_class, wdm/DIRECTORY_NOTIFY_INFORMATION_CLASS, wdm/DirectoryNotifyExtendedInformation, wdm/DirectoryNotifyInformation"
ms.topic: enum
req.header: wdm.h
req.include-header: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DIRECTORY_NOTIFY_INFORMATION_CLASS
product:
- Windows
targetos: Windows
req.typenames: DIRECTORY_NOTIFY_INFORMATION_CLASS, *PDIRECTORY_NOTIFY_INFORMATION_CLASS
---

# _DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

A value that specifies which structure to use to query or set information for a files in a directory.


## -enum-fields




### -field DirectoryNotifyInformation

A <b>FILE_NOTIFY_INFORMATION </b>structure.


### -field DirectoryNotifyExtendedInformation

A <b>FILE_NOTIFY_EXTENDED_INFORMATION</b> structure.

