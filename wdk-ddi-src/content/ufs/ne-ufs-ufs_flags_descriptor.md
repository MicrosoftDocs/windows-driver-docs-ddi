---
UID: NE:ufs.UFS_FLAGS_DESCRIPTOR
title: UFS_FLAGS_DESCRIPTOR
author: windows-driver-content
description: UFS_FLAGS_DESCRIPTOR describes the different types of flags used by Universal Flash Storage (UFS) descriptors.
old-location: storage\ufs_flags_descriptor.htm
old-project: storage
ms.assetid: D530355F-5824-4F7C-84C4-57D3D03A7116
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: UFS_FLAGS_DESCRIPTOR, UFS_FLAGS_DESCRIPTOR enumeration [Storage Devices], UFS_Reserved1, UFS_Reserved2, UFS_Reserved3, UFS_Reserved4, UFS_Reserved5, UFS_fBackgroundOpsEn, UFS_fBusyRTC, UFS_fDeviceInit, UFS_fDeviceLifeSpanModeEn, UFS_fPermanentWPEn, UFS_fPermanentlyDisableFwUpdate, UFS_fPhyResourceRemoval, UFS_fPowerOnWPEn, UFS_fPurgeEnable, storage.ufs_flags_descriptor, ufs/UFS_FLAGS_DESCRIPTOR, ufs/UFS_Reserved1, ufs/UFS_Reserved2, ufs/UFS_Reserved3, ufs/UFS_Reserved4, ufs/UFS_Reserved5, ufs/UFS_fBackgroundOpsEn, ufs/UFS_fBusyRTC, ufs/UFS_fDeviceInit, ufs/UFS_fDeviceLifeSpanModeEn, ufs/UFS_fPermanentWPEn, ufs/UFS_fPermanentlyDisableFwUpdate, ufs/UFS_fPhyResourceRemoval, ufs/UFS_fPowerOnWPEn, ufs/UFS_fPurgeEnable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ufs.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ufs.h
api_name:
-	UFS_FLAGS_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_FLAGS_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_FLAGS_DESCRIPTOR enumeration


## -description


<b>UFS_FLAGS_DESCRIPTOR</b> describes the different types of flags used by Universal Flash Storage (UFS) descriptors.


## -enum-fields




### -field UFS_Reserved1

Reserved for future use.


### -field UFS_fDeviceInit

Indicates the device initialization is in progress.


### -field UFS_fPermanentWPEn

Indicates permanent write protection is enabled.


### -field UFS_fPowerOnWPEn

Indicates power on write protection is enabled.


### -field UFS_fBackgroundOpsEn

Indicates the device is permitted to run
background operations.


### -field UFS_fDeviceLifeSpanModeEn

Indicates Device Life Span Mode is enabled.


### -field UFS_fPurgeEnable

Indicates Purge Operation is enabled.


### -field UFS_Reserved2

Reserved for future use.


### -field UFS_fPhyResourceRemoval

Indicates
that the dynamic capacity operation occurs on the device's EndPointReset or
a hardware reset. The host cannot reset this flag.


### -field UFS_fBusyRTC

Indicates the device is executing internal
operation related to Real Time Clock.


### -field UFS_Reserved3

Reserved for the Unified Memory Extension standard..


### -field UFS_fPermanentlyDisableFwUpdate

Indicates the UFS device will permanently
disallow future firmware updates to
the Universal Flash Storage (UFS) device.


### -field UFS_Reserved4

Reserved for the Unified Memory Extension standard.


### -field UFS_Reserved5

Reserved for the Unified Memory Extension standard.

