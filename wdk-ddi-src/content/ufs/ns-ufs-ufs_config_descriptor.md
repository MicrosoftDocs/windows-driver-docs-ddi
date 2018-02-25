---
UID: NS:ufs.UFS_CONFIG_DESCRIPTOR
title: UFS_CONFIG_DESCRIPTOR
author: windows-driver-content
description: The UFS_CONFIG_DESCRIPTOR structure describes the modifiable values of the default device configuration set by the manufacturer.
old-location: storage\ufs_config_descriptor.htm
old-project: storage
ms.assetid: B65A2268-6959-4630-97DA-C0CFD37D9174
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PUFS_CONFIG_DESCRIPTOR, ,, C, D, E, F, G, I, N, O, P, PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR structure pointer [Storage Devices], R, S, T, U, UFS_CONFIG_DESCRIPTOR, UFS_CONFIG_DESCRIPTOR structure [Storage Devices], _, storage.ufs_config_descriptor, ufs/PUFS_CONFIG_DESCRIPTOR, ufs/UFS_CONFIG_DESCRIPTOR"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ufs.h
apiname:
-	UFS_CONFIG_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_CONFIG_DESCRIPTOR structure


## -description


The <b>UFS_CONFIG_DESCRIPTOR</b> structure describes the modifiable values of the default device configuration set by the manufacturer. 


## -syntax


````
typedef struct _UFS_CONFIG_DESCRIPTOR {
  UCHAR                       bLength;
  UCHAR                       bDescriptorIDN;
  UCHAR                       Reserved1;
  UCHAR                       bBootEnable;
  UCHAR                       bDescrAccessEn;
  UCHAR                       bInitPowerMode;
  UCHAR                       bHighPriorityLUN;
  UCHAR                       bSecureRemovalType;
  UCHAR                        bInitActiveICCLevel;
  UCHAR                       wPeriodicRTCUpdate[2];
  UCHAR                        Reserved2[5];
   UFS_UNIT_CONFIG_DESCRIPTOR UnitConfig[UFS_MAX_NUM_LU];
} UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR;
````


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

<a href="..\ufs\ns-ufs-ufs_unit_config_descriptor.md">UFS_UNIT_CONFIG_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20UFS_CONFIG_DESCRIPTOR structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

