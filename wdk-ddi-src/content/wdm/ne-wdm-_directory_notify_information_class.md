---
UID: NE:wdm._DIRECTORY_NOTIFY_INFORMATION_CLASS
title: "_DIRECTORY_NOTIFY_INFORMATION_CLASS"
author: windows-driver-content
description: A value that specifies which structure to use to query or set information for a files in a directory.
old-location: ifsk\_directory_notify_information_class.htm
old-project: ifsk
ms.assetid: 77c2515b-f20a-47ac-9564-9eab009cf625
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: wdm/DIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS, wdm/DirectoryNotifyExtendedInformation, _DIRECTORY_NOTIFY_INFORMATION_CLASS, ifsk._directory_notify_information_class, DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration [Kernel-Mode Driver Architecture], DirectoryNotifyInformation, wdm/DirectoryNotifyInformation, *PDIRECTORY_NOTIFY_INFORMATION_CLASS, DirectoryNotifyExtendedInformation
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	DIRECTORY_NOTIFY_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: "*PDIRECTORY_NOTIFY_INFORMATION_CLASS, DIRECTORY_NOTIFY_INFORMATION_CLASS"
req.product: Windows 10 or later.
---

# _DIRECTORY_NOTIFY_INFORMATION_CLASS enumeration


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

A value that specifies which structure to use to query or set information for a files in a directory.


## -syntax


````
typedef enum _DIRECTORY_NOTIFY_INFORMATION_CLASS { 
  DirectoryNotifyInformation          = 1,
  DirectoryNotifyExtendedInformation
} DIRECTORY_NOTIFY_INFORMATION_CLASS;
````


## -enum-fields




### -field DirectoryNotifyInformation

A <b>FILE_NOTIFY_INFORMATION </b>structure.


### -field DirectoryNotifyExtendedInformation

A <b>FILE_NOTIFY_EXTENDED_INFORMATION</b> structure.

