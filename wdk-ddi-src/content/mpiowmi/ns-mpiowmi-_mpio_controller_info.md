---
UID: NS:mpiowmi._MPIO_CONTROLLER_INFO
title: "_MPIO_CONTROLLER_INFO" (mpiowmi.h)
description: The MPIO_CONTROLLER_INFO structure represents a storage controller.
old-location: storage\mpio_controller_info.htm
tech.root: storage
ms.assetid: 30600e86-dd35-4498-91a8-14a722b2e868
ms.date: 03/29/2018
ms.keywords: "*PMPIO_CONTROLLER_INFO, MPIO_CONTROLLER_INFO, MPIO_CONTROLLER_INFO structure [Storage Devices], PMPIO_CONTROLLER_INFO, PMPIO_CONTROLLER_INFO structure pointer [Storage Devices], _MPIO_CONTROLLER_INFO, mpiowmi/MPIO_CONTROLLER_INFO, mpiowmi/PMPIO_CONTROLLER_INFO, storage.mpio_controller_info, structs-scsibus_6b7edecb-9938-49fb-8367-5d176f83c0a5.xml"
ms.topic: struct
req.header: mpiowmi.h
req.include-header: Mpiowmi.h
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
-	mpiowmi.h
api_name:
-	MPIO_CONTROLLER_INFO
product:
- Windows
targetos: Windows
req.typenames: MPIO_CONTROLLER_INFO, *PMPIO_CONTROLLER_INFO
---

# _MPIO_CONTROLLER_INFO structure


## -description


The MPIO_CONTROLLER_INFO structure represents a storage controller.


## -struct-fields




### -field IdentifierType

An unsigned 32-bitfield that represents the identifier type for the controller.


### -field IdentifierLength

An unsigned 32-bitfield that represents the length of the controller's identifier.


### -field Identifier

A 32-byte array that contains the actual identifier (serial number) of the controller.


### -field ControllerState

An unsigned 32-bitfield that represents the controller state.


### -field Pad

Should be zero.


### -field AssociatedDsm

A string field of maximum length 63 characters. This string field returns the friendly name of the DSM that controls the devices that are exposed by this controller.

