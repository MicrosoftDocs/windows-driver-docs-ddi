---
UID: NS:ufs.UFS_CONFIG_DESCRIPTOR
title: UFS_CONFIG_DESCRIPTOR
author: windows-driver-content
description: The UFS_CONFIG_DESCRIPTOR structure describes the modifiable values of the default device configuration set by the manufacturer.
old-location: storage\ufs_config_descriptor.htm
old-project: storage
ms.assetid: B65A2268-6959-4630-97DA-C0CFD37D9174
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR structure pointer [Storage Devices], UFS_CONFIG_DESCRIPTOR, UFS_CONFIG_DESCRIPTOR structure [Storage Devices], storage.ufs_config_descriptor, ufs/PUFS_CONFIG_DESCRIPTOR, ufs/UFS_CONFIG_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	UFS_CONFIG_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_CONFIG_DESCRIPTOR structure


## -description


The <b>UFS_CONFIG_DESCRIPTOR</b> structure describes the modifiable values of the default device configuration set by the manufacturer. 


## -struct-fields




### -field bLength

Specifies the size, in bytes, of this descriptor.


### -field bDescriptorIDN

Specifies the Configuration Descriptor Type Identifier. This descriptor will have a value of <b>UFS_DESC_CONFIGURATION_IDN</b>.


### -field Reserved1

Reserved for future use.


### -field bBootEnable

Specifies if a device's boot feature is enabled.


### -field bDescrAccessEn

Enables access to the Device Descriptor after the
partial initialization phase of the boot sequence.


### -field bInitPowerMode

Specifies the power mode after device initialization
or hardware reset.


### -field bHighPriorityLUN

<b>bHighPriorityLUN</b> configures the high priority logical unit.


### -field bSecureRemovalType

Configures the secure removal type.


### -field bInitActiveICCLevel

Configures the ICC level in Active mode after device
initialization or hardware reset.


### -field wPeriodicRTCUpdate

Specifies the frequency and method of real-time clock updates.


### -field Reserved2

Reserved for future use.


### -field UnitConfig

Contains the configurable parameters of the Unit Descriptor. 


## -see-also




<a href="https://msdn.microsoft.com/09CBAD0A-CBDC-464E-908C-BF142D515969">UFS_UNIT_CONFIG_DESCRIPTOR</a>
 

 

