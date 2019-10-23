---
UID: NS:wiamindr_lh._WIA_DEV_CAP_DRV
title: _WIA_DEV_CAP_DRV (wiamindr_lh.h)
description: The WIA_DEV_CAP_DRV structure is used to enumerate device capabilities. A device capability is defined by an event or command that the device supports.
old-location: image\wia_dev_cap_drv.htm
tech.root: image
ms.assetid: 4024d455-2393-481f-8cb5-b33346ca85c7
ms.date: 05/03/2018
ms.keywords: "*PWIA_DEV_CAP_DRV, PWIA_DEV_CAP_DRV, PWIA_DEV_CAP_DRV structure pointer [Imaging Devices], WIA_DEV_CAP_DRV, WIA_DEV_CAP_DRV structure [Imaging Devices], _WIA_DEV_CAP_DRV, image.wia_dev_cap_drv, wiamindr_lh/PWIA_DEV_CAP_DRV, wiamindr_lh/WIA_DEV_CAP_DRV, wiastrct_111f0703-6db4-4a87-ae12-20a3120219cc.xml"
ms.topic: struct
f1_keywords:
 - "wiamindr_lh/WIA_DEV_CAP_DRV"
req.header: wiamindr_lh.h
req.include-header: Wiamindr.h
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
- wiamindr_lh.h
api_name:
- WIA_DEV_CAP_DRV
product:
- Windows
targetos: Windows
req.typenames: WIA_DEV_CAP_DRV, *PWIA_DEV_CAP_DRV
---

# _WIA_DEV_CAP_DRV structure

## -description

The WIA_DEV_CAP_DRV structure is used to enumerate device capabilities. A device capability is defined by an event or command that the device supports.

## -struct-fields

### -field guid

Points to a GUID that identifies the device capability. This member can be set to any of the values specified for WIA device commands (WIA_CMD_*XXX* commands) or WIA event identifiers (WIA_EVENT_*XXX* event identifiers). For more information, see [WIA Device Commands](https://docs.microsoft.com/windows/win32/wia/-wia-wia-device-commands).

The driver can define its own capability GUID that it can send down to the device. An application would need to have specific knowledge about that capability in order for it to be able to respond to the new capability, however. An application normally recognizes only the standard WIA command and event GUIDs (WIA_CMD_XXX and WIA_EVENT_XXX).

### -field ulFlags

Specifies the type of event. This member can be set to one or both of the following:

| Flag | Meaning |
| --- | --- |
| WIA_ACTION_EVENT | Application can register action for the given event using the [IWiaDevMgr::RegisterEventCallbackProgram](https://docs.microsoft.com/windows/win32/api/wia_xp/nf-wia_xp-iwiadevmgr-registereventcallbackprogram) and [IwiaDevMgr::RegisterEventCallbackCLSID](https://docs.microsoft.com/windows/win32/api/wia_xp/nf-wia_xp-iwiadevmgr-registereventcallbackclsid) methods. An action event launches the application that is registered to handle such an event. |
| WIA_NOTIFICATION_EVENT | Application can register for notification on the given event using the [IwiaDevMgr::RegisterEventCallbackInterface](https://docs.microsoft.com/windows/win32/api/wia_xp/nf-wia_xp-iwiadevmgr-registereventcallbackinterface) method. A notification event is sent only to applications that are already running. |

### -field wszName

Specifies a string that contains a short version of the capability name.

### -field wszDescription

Specifies a string containing the version of the capability name that can be displayed to the user.

### -field wszIcon

Specifies a string containing the name of the icon for this capability. The icon can be displayed to the user .

## -remarks

The WIA service calls the minidriver's [IWiaMiniDrv::drvGetCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities) function to fill in the members of a WIA_DEV_CAP_DRV structure.

When a driver is enumerating event handlers, the only valid value is WIA_IS_DEFAULT_HANDLER; which indicates that the currently registered handler should be used.

## -see-also

[Driver Capabilities](https://docs.microsoft.com/windows-hardware/drivers/image/driver-capabilities)

[IWiaMiniDrv::drvGetCapabilities](https://docs.microsoft.com/windows-hardware/drivers/ddi/wiamindr_lh/nf-wiamindr_lh-iwiaminidrv-drvgetcapabilities)
