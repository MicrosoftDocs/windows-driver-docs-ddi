---
UID: NE:wudfwdm.DEVICE_REGISTRY_PROPERTY
title: DEVICE_REGISTRY_PROPERTY
author: windows-driver-content
description: The DEVICE_REGISTRY_PROPERTY enumeration identifies device properties that are stored in the registry.
old-location: kernel\device_registry_property.htm
old-project: kernel
ms.assetid: a17b4a88-45e8-45e7-b879-2f41b97be368
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: DEVICE_REGISTRY_PROPERTY, DEVICE_REGISTRY_PROPERTY enumeration [Kernel-Mode Driver Architecture], DevicePropertyAddress, DevicePropertyAllocatedResources, DevicePropertyBootConfiguration, DevicePropertyBootConfigurationTranslated, DevicePropertyBusNumber, DevicePropertyBusTypeGuid, DevicePropertyClassGuid, DevicePropertyClassName, DevicePropertyCompatibleIDs, DevicePropertyContainerID, DevicePropertyDeviceDescription, DevicePropertyDriverKeyName, DevicePropertyEnumeratorName, DevicePropertyFriendlyName, DevicePropertyHardwareID, DevicePropertyInstallState, DevicePropertyLegacyBusType, DevicePropertyLocationInformation, DevicePropertyManufacturer, DevicePropertyPhysicalDeviceObjectName, DevicePropertyRemovalPolicy, DevicePropertyResourceRequirements, DevicePropertyUINumber, enumeration [Kernel-Mode Driver Architecture], kernel.device_registry_property, sysenum_485e3369-186a-4a71-b13e-be6ff9ab8dce.xml, wdm/, wdm/DevicePropertyAddress, wdm/DevicePropertyAllocatedResources, wdm/DevicePropertyBootConfiguration, wdm/DevicePropertyBootConfigurationTranslated, wdm/DevicePropertyBusNumber, wdm/DevicePropertyBusTypeGuid, wdm/DevicePropertyClassGuid, wdm/DevicePropertyClassName, wdm/DevicePropertyCompatibleIDs, wdm/DevicePropertyContainerID, wdm/DevicePropertyDeviceDescription, wdm/DevicePropertyDriverKeyName, wdm/DevicePropertyEnumeratorName, wdm/DevicePropertyFriendlyName, wdm/DevicePropertyHardwareID, wdm/DevicePropertyInstallState, wdm/DevicePropertyLegacyBusType, wdm/DevicePropertyLocationInformation, wdm/DevicePropertyManufacturer, wdm/DevicePropertyPhysicalDeviceObjectName, wdm/DevicePropertyRemovalPolicy, wdm/DevicePropertyResourceRequirements, wdm/DevicePropertyUINumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: Called at IRQL <= DISPATCH_LEVEL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DEVICE_REGISTRY_PROPERTY
product: Windows
targetos: Windows
req.typenames: DEVICE_REGISTRY_PROPERTY
req.product: Windows 10 or later.
---

# DEVICE_REGISTRY_PROPERTY enumeration


## -description


The <b>DEVICE_REGISTRY_PROPERTY</b> enumeration identifies device properties that are stored in the registry.


## -syntax


````
typedef enum  { 
  DevicePropertyDeviceDescription            = 0x0,
  DevicePropertyHardwareID                   = 0x1,
  DevicePropertyCompatibleIDs                = 0x2,
  DevicePropertyBootConfiguration            = 0x3,
  DevicePropertyBootConfigurationTranslated  = 0x4,
  DevicePropertyClassName                    = 0x5,
  DevicePropertyClassGuid                    = 0x6,
  DevicePropertyDriverKeyName                = 0x7,
  DevicePropertyManufacturer                 = 0x8,
  DevicePropertyFriendlyName                 = 0x9,
  DevicePropertyLocationInformation          = 0xa,
  DevicePropertyPhysicalDeviceObjectName     = 0xb,
  DevicePropertyBusTypeGuid                  = 0xc,
  DevicePropertyLegacyBusType                = 0xd,
  DevicePropertyBusNumber                    = 0xe,
  DevicePropertyEnumeratorName               = 0xf,
  DevicePropertyAddress                      = 0x10,
  DevicePropertyUINumber                     = 0x11,
  DevicePropertyInstallState                 = 0x12,
  DevicePropertyRemovalPolicy                = 0x13,
  DevicePropertyResourceRequirements         = 0x14,
  DevicePropertyAllocatedResources           = 0x15,
  DevicePropertyContainerID                  = 0x16
} DEVICE_REGISTRY_PROPERTY;
````


## -enum-fields




### -field DevicePropertyDeviceDescription


### -field DevicePropertyHardwareID


### -field DevicePropertyCompatibleIDs


### -field DevicePropertyBootConfiguration


### -field DevicePropertyBootConfigurationTranslated


### -field DevicePropertyClassName


### -field DevicePropertyClassGuid


### -field DevicePropertyDriverKeyName


### -field DevicePropertyManufacturer


### -field DevicePropertyFriendlyName


### -field DevicePropertyLocationInformation


### -field DevicePropertyPhysicalDeviceObjectName


### -field DevicePropertyBusTypeGuid


### -field DevicePropertyLegacyBusType


### -field DevicePropertyBusNumber


### -field DevicePropertyEnumeratorName


### -field DevicePropertyAddress


### -field DevicePropertyUINumber


### -field DevicePropertyInstallState


### -field DevicePropertyRemovalPolicy


### -field DevicePropertyResourceRequirements


### -field DevicePropertyAllocatedResources


### -field DevicePropertyContainerID


## -see-also

<a href="..\wdm\nf-wdm-iogetdeviceproperty.md">IoGetDeviceProperty</a>



 

 


