---
UID: NE:srb.__unnamed_enum_0
title: STOR_POWER_ACTION (srb.h)
description: The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition.
old-location: storage\stor_power_action.htm
tech.root: storage
ms.assetid: ffc7c1ec-faec-4383-ab69-844cf68d054f
ms.date: 03/29/2018
ms.keywords: "*PSTOR_POWER_ACTION, PSTOR_POWER_ACTION, PSTOR_POWER_ACTION enumeration pointer [Storage Devices], STOR_POWER_ACTION, STOR_POWER_ACTION enumeration [Storage Devices], StorPowerActionHibernate, StorPowerActionNone, StorPowerActionReserved, StorPowerActionShutdown, StorPowerActionShutdownOff, StorPowerActionShutdownReset, StorPowerActionSleep, StorPowerActionWarmEject, storage.stor_power_action, storport/PSTOR_POWER_ACTION, storport/STOR_POWER_ACTION, storport/StorPowerActionHibernate, storport/StorPowerActionNone, storport/StorPowerActionReserved, storport/StorPowerActionShutdown, storport/StorPowerActionShutdownOff, storport/StorPowerActionShutdownReset, storport/StorPowerActionSleep, storport/StorPowerActionWarmEject, structs-storport_53754a67-bd34-4f06-92ba-2f45d7fa66a9.xml"
ms.topic: enum
f1_keywords:
 - "srb/STOR_POWER_ACTION"
req.header: srb.h
req.include-header: Storport.h, Minitape.h, Srb.h
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- storport.h
api_name:
- STOR_POWER_ACTION
product:
- Windows
targetos: Windows
req.typenames: STOR_POWER_ACTION, *PSTOR_POWER_ACTION
---

# STOR_POWER_ACTION enumeration


## -description


The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. 


## -enum-fields




### -field StorPowerActionNone

No system shutdown is about to occur.


### -field StorPowerActionReserved

Reserved.


### -field StorPowerActionSleep

The system is entering standby.


### -field StorPowerActionHibernate

The system is entering hibernation.


### -field StorPowerActionShutdown

The system is shutting down, but the type of shutdown is not known.


### -field StorPowerActionShutdownReset

The system is shutting down and resetting.


### -field StorPowerActionShutdownOff

The system is shutting down and powering off.


### -field StorPowerActionWarmEject

The system is preparing for ejection.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/storport/ns-storport-_scsi_power_request_block">SCSI_POWER_REQUEST_BLOCK</a>
 

 

