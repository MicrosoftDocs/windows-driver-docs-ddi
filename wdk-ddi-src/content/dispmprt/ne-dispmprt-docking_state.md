---
UID: NE:dispmprt.DOCKING_STATE
title: DOCKING_STATE
author: windows-driver-content
description: The DOCKING_STATE enumeration is used to describe the state of a portable computer that can be attached to a docking station.
old-location: display\docking_state.htm
old-project: display
ms.assetid: 4e051d49-57ae-43c8-a894-a6c2c277dce9
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dispmprt/DockStateUnsupported, DockStateDocked, DmEnums_1a20e5b4-8df9-4298-8661-d7697d99e139.xml, DOCKING_STATE enumeration [Display Devices], DOCKING_STATE, DockStateUnDocked, dispmprt/DockStateUnknown, display.docking_state, dispmprt/DockStateDocked, DockStateUnknown, dispmprt/DOCKING_STATE, DockStateUnsupported, dispmprt/DockStateUnDocked
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	dispmprt.h
apiname:
-	DOCKING_STATE
product: Windows
targetos: Windows
req.typenames: DOCKING_STATE
---

# DOCKING_STATE enumeration


## -description


The DOCKING_STATE enumeration is used to describe the state of a portable computer that can be attached to a docking station.


## -syntax


````
typedef enum  { 
  DockStateUnsupported  = 0,
  DockStateUnDocked     = 1,
  DockStateDocked       = 2,
  DockStateUnknown      = 3
} DOCKING_STATE;
````


## -enum-fields




### -field DockStateUnsupported

Indicates that the portable computer does not support docking.


### -field DockStateUnDocked

Indicates that the portable computer is not docked.


### -field DockStateDocked

Indicates that the portable computer is docked.


### -field DockStateUnknown

Indicates that the docking state of the portable computer is not known.

