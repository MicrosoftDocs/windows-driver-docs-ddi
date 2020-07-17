---
UID: NS:ntpoapi._PO_SPR_ACTIVE_SESSION_DATA
title: _PO_SPR_ACTIVE_SESSION_DATA (ntpoapi.h)
description: Allow drivers to register/unregister for SPR Active session start and end notifications.
tech.root: kernel
ms.assetid: b3d767f3-3545-4f88-8aa2-8e625d657ac2
ms.date: 10/19/2018
keywords: ["_PO_SPR_ACTIVE_SESSION_DATA structure"]
f1_keywords:
 - "ntpoapi/_PO_SPR_ACTIVE_SESSION_DATA"
 - "_PO_SPR_ACTIVE_SESSION_DATA"
ms.keywords: _PO_SPR_ACTIVE_SESSION_DATA, *PPO_SPR_ACTIVE_SESSION_DATA, PO_SPR_ACTIVE_SESSION_DATA, 
req.header: ntpoapi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: PO_SPR_ACTIVE_SESSION_DATA, *PPO_SPR_ACTIVE_SESSION_DATA
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location:
- ntpoapi.h
api_name: 
- _PO_SPR_ACTIVE_SESSION_DATA
product:
- Windows
targetos: Windows
---

# _PO_SPR_ACTIVE_SESSION_DATA structure

## -description

Stores information that indicates whether a System Power Report's Active Session is starting or ending. 

## -struct-fields

### -field Start
A boolean value that indicates whether the session is starting or ending.

### -field ActiveSessionGuid
The Active session GUID for the session.

## -remarks

To register for System Power Report's Active Session notifications, you must call [**PowerSettingRegisterNotification**](https://docs.microsoft.com/windows/desktop/api/powersetting/nf-powersetting-powersettingregisternotification) function with these values:

- _SettingGuid_: Pass GUID_SPR_ACTIVE_SESSION_CHANGE.
- _Flags_: Set to DEVICE_NOTIFY_CALLBACK. 
- _Recipient_: A [**DEVICE_NOTIFY_SUBSCRIBE_PARAMETERS**](https://docs.microsoft.com/windows/desktop/api/powersetting/nf-powersetting-powersettingregisternotification) structure, in which the **Callback** member is set to your implementation of the [DEVICE_NOTIFY_CALLBACK_ROUTINE](https://docs.microsoft.com/windows/desktop/api/powrprof/nc-powrprof-device_notify_callback_routine) callback routine  that gets called when the session starts or ends.

If the registration is successful, the [DEVICE_NOTIFY_CALLBACK_ROUTINE](https://docs.microsoft.com/windows/desktop/api/powrprof/nc-powrprof-device_notify_callback_routine) callback is invoked with these value:

- _Type_: PBT_POWERSETTINGCHANGE to indicate a power setting change.
- _UpdateSetting_: Is a [**POWERBROADCAST_SETTING**](https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-powerbroadcast_setting) structure; the **PowerSetting** member is set to GUID_SPR_ACTIVE_SESSION_CHANGE, the **DataLength** member is a **_PO_SPR_ACTIVE_SESSION_DATA** structure.

## -see-also
[**PowerSettingRegisterNotification**](https://docs.microsoft.com/windows/desktop/api/powersetting/nf-powersetting-powersettingregisternotification)

[**POWERBROADCAST_SETTING**](https://docs.microsoft.com/windows/desktop/api/winuser/ns-winuser-powerbroadcast_setting)

[DEVICE_NOTIFY_CALLBACK_ROUTINE](https://docs.microsoft.com/windows/desktop/api/powrprof/nc-powrprof-device_notify_callback_routine)
