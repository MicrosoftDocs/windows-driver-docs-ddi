---
UID: NE:minitape.PSTOR_POWER_ACTION
title: "*PSTOR_POWER_ACTION"
author: windows-driver-content
description: The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition.
old-location: storage\stor_power_action.htm
old-project: storage
ms.assetid: ffc7c1ec-faec-4383-ab69-844cf68d054f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storport/StorPowerActionNone, structs-storport_53754a67-bd34-4f06-92ba-2f45d7fa66a9.xml, storage.stor_power_action, storport/STOR_POWER_ACTION, StorPowerActionHibernate, storport/StorPowerActionShutdown, StorPowerActionWarmEject, *PSTOR_POWER_ACTION, StorPowerActionSleep, StorPowerActionShutdownOff, storport/StorPowerActionShutdownOff, storport/StorPowerActionShutdownReset, StorPowerActionReserved, PSTOR_POWER_ACTION, storport/StorPowerActionWarmEject, STOR_POWER_ACTION, StorPowerActionShutdownReset, storport/PSTOR_POWER_ACTION, STOR_POWER_ACTION enumeration [Storage Devices], PSTOR_POWER_ACTION enumeration pointer [Storage Devices], storport/StorPowerActionReserved, StorPowerActionShutdown, storport/StorPowerActionSleep, StorPowerActionNone, storport/StorPowerActionHibernate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: minitape.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	STOR_POWER_ACTION
product: Windows
targetos: Windows
req.typenames: STOR_POWER_ACTION, *PSTOR_POWER_ACTION
---

# *PSTOR_POWER_ACTION enumeration


## -description


The STOR_POWER_ACTION enumerator indicates the power state that the system is about to enter during a power transition. 


## -syntax


````
typedef enum  { 
  StorPowerActionNone           = 0,
  StorPowerActionReserved       = 1,
  StorPowerActionSleep          = 2,
  StorPowerActionHibernate      = 3,
  StorPowerActionShutdown       = 4,
  StorPowerActionShutdownReset  = 5,
  StorPowerActionShutdownOff    = 6,
  StorPowerActionWarmEject      = 7
} STOR_POWER_ACTION, *PSTOR_POWER_ACTION;
````


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

<a href="..\minitape\ns-minitape-_scsi_power_request_block.md">SCSI_POWER_REQUEST_BLOCK</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20STOR_POWER_ACTION enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

