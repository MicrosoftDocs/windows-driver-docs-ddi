---
UID: NE:ucmtypes._UCM_POWER_ROLE
title: "_UCM_POWER_ROLE"
author: windows-driver-content
description: Defines power roles of USB Type-C connected devices.
old-location: buses\ucm_power_role.htm
old-project: usbref
ms.assetid: 005B2A80-F6F8-42DA-86C3-277676B9168A
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ucm_power_role, _UCM_POWER_ROLE, ucmtypes/UcmPowerRoleSink, UcmPowerRoleSink, ucmtypes/UCM_POWER_ROLE, UcmPowerRoleSource, ucmtypes/UcmPowerRoleSource, ucmtypes/UcmPowerRoleInvalid, UCM_POWER_ROLE enumeration [Buses], UCM_POWER_ROLE, UcmPowerRoleInvalid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmtypes.h
apiname:
-	UCM_POWER_ROLE
product: Windows
targetos: Windows
req.typenames: UCM_POWER_ROLE
req.product: Windows 10 or later.
---

# _UCM_POWER_ROLE enumeration


## -description


Defines power roles of USB Type-C connected devices. 


## -syntax


````
typedef enum _UCM_POWER_ROLE { 
  UcmPowerRoleInvalid  = 0x0,
  UcmPowerRoleSink     = 0x1,
  UcmPowerRoleSource   = 0x2
} UCM_POWER_ROLE;
````


## -enum-fields




### -field UcmPowerRoleInvalid

Indicates the power role state is invalid.


### -field UcmPowerRoleSink

Indicates the power role is set to sink power.


### -field UcmPowerRoleSource

Indicates the power role is set to source power. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187914">UcmConnectorPowerDirectionChanged</a>

<a href="..\ucmmanager\nc-ucmmanager-evt_ucm_connector_set_power_role.md">EVT_UCM_CONNECTOR_SET_POWER_ROLE</a>

<a href="..\ucmmanager\ns-ucmmanager-_ucm_connector_pd_config.md">UCM_CONNECTOR_PD_CONFIG</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_POWER_ROLE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

