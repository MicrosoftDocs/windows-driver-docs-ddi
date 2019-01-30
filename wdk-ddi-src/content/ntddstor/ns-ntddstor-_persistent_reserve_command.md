---
UID: NS:ntddstor._PERSISTENT_RESERVE_COMMAND
title: "_PERSISTENT_RESERVE_COMMAND" (ntddstor.h)
description: The PERSISTENT_RESERVE_COMMAND structure is used together with the IOCTL_STORAGE_PERSISTENT_RESERVE_IN and IOCTL_STORAGE_PERSISTENT_RESERVE_OUT requests to obtain and control information about persistent reservations and reservation keys that are active within a device server.
old-location: storage\persistent_reserve_command.htm
tech.root: storage
ms.assetid: c7debd93-0fcd-43c5-a950-8154b62175bf
ms.date: 03/29/2018
ms.keywords: "*PPERSISTENT_RESERVE_COMMAND, PERSISTENT_RESERVE_COMMAND, PERSISTENT_RESERVE_COMMAND structure [Storage Devices], PPERSISTENT_RESERVE_COMMAND, PPERSISTENT_RESERVE_COMMAND structure pointer [Storage Devices], _PERSISTENT_RESERVE_COMMAND, ntddstor/PERSISTENT_RESERVE_COMMAND, ntddstor/PPERSISTENT_RESERVE_COMMAND, storage.persistent_reserve_command, structs-general_4fe3d6f6-6e9f-41f5-915c-2636707f429c.xml"
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddstor.h
api_name:
-	PERSISTENT_RESERVE_COMMAND
product:
- Windows
targetos: Windows
req.typenames: PERSISTENT_RESERVE_COMMAND, *PPERSISTENT_RESERVE_COMMAND
---

# _PERSISTENT_RESERVE_COMMAND structure


## -description


The PERSISTENT_RESERVE_COMMAND structure is used together with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560582">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560586">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a> requests to obtain and control information about persistent reservations and reservation keys that are active within a device server.


## -struct-fields




### -field Version

The version of this structure.


### -field Size

The size of this structure.


### -field DUMMYUNIONNAME

 


### -field DUMMYUNIONNAME.PR_IN


### -field DUMMYUNIONNAME.PR_IN.ServiceAction

The service action code for this IOCTL_STORAGE_PERSISTENT_RESERVE_IN request. PR_IN.ServiceAction can be one of the following values:
RESERVATION_ACTION_READ_KEYS
RESERVATION_ACTION_READ_RESERVATIONS



### -field DUMMYUNIONNAME.PR_IN.Reserved1

Reserved. Must be zero.


### -field DUMMYUNIONNAME.PR_IN.AllocationLength

The number of bytes allocated for the returned parameter list.


### -field DUMMYUNIONNAME.PR_OUT


### -field DUMMYUNIONNAME.PR_OUT.ServiceAction

The service action code for this IOCTL_STORAGE_PERSISTENT_RESERVE_OUT request. PR_OUT.ServiceAction can be one of the following values:
RESERVATION_ACTION_REGISTER
RESERVATION_ACTION_RESERVE
RESERVATION_ACTION_RELEASE
RESERVATION_ACTION_CLEAR
RESERVATION_ACTION_PREEMPT
RESERVATION_ACTION_PREEMPT_ABORT
RESERVATION_ACTION_REGISTER_IGNORE_EXISTING



### -field DUMMYUNIONNAME.PR_OUT.Reserved1

Reserved. Must be zero.


### -field DUMMYUNIONNAME.PR_OUT.Type

A value that specifies the characteristics of the persistent reservation. PR_OUT.Type can be one of the following values:
RESERVATION_TYPE_WRITE_EXCLUSIVE
RESERVATION_TYPE_EXCLUSIVE
RESERVATION_TYPE_WRITE_EXCLUSIVE_REGISTRANTS
RESERVATION_TYPE_EXCLUSIVE_REGISTRANTS



### -field DUMMYUNIONNAME.PR_OUT.Scope

A value that specifies whether the persistent reservation applies to the entire logical unit or a specific element of the logical unit. PR_OUT.Scope can be one of the following values:
RESERVATION_SCOPE_LU
RESERVATION_SCOPE_ELEMENT



### -field DUMMYUNIONNAME.PR_OUT.ParameterList

The space for additional SCSI Persistent Reserve Out command parameters.


## -remarks



The behavior of the storage device when a SCSI Persistent Reserve In command or a SCSI Persistent Reserve Out command is received is described in the <a href="https://go.microsoft.com/fwlink/p/?linkid=153142">SCSI Primary Commands - 2 (SPC-2)</a> specification.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560582">IOCTL_STORAGE_PERSISTENT_RESERVE_IN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560586">IOCTL_STORAGE_PERSISTENT_RESERVE_OUT</a>
 

 

