---
UID: NE:urstypes._URS_ROLE
title: _URS_ROLE (urstypes.h)
description: Defines values for roles supported by a USB dual-role controller.
old-location: buses\urs_role.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["URS_ROLE enumeration"]
ms.keywords: "*PURS_ROLE, URS_ROLE, URS_ROLE enumeration [Buses], URS_ROLE,*PURS_ROLE, URS_ROLE,*PURS_ROLE enumeration [Buses], UrsRoleFunction, UrsRoleHost, UrsRoleNone, _URS_ROLE, buses.urs_role, urstypes/URS_ROLE, urstypes/UrsRoleFunction, urstypes/UrsRoleHost, urstypes/UrsRoleNone"
req.header: urstypes.h
req.include-header: Urstypes.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
targetos: Windows
req.typenames: URS_ROLE, *PURS_ROLE
f1_keywords:
 - _URS_ROLE
 - urstypes/_URS_ROLE
 - PURS_ROLE
 - urstypes/PURS_ROLE
 - URS_ROLE
 - urstypes/URS_ROLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Urstypes.h
api_name:
 - URS_ROLE, *PURS_ROLE
---

# _URS_ROLE enumeration


## -description

Defines values for roles supported by a USB dual-role controller.

## -enum-fields

### -field UrsRoleNone

Internal use only. Must be 0.

### -field UrsRoleHost

Indicates the host role of the controller.

### -field UrsRoleFunction

Indicates the function role of the controller.

