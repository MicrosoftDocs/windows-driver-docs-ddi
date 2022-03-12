---
UID: NS:wwan._WWAN_READY_INFO_REV2_PRE2170
tech.root: netvista
title: WWAN_READY_INFO_REV2_PRE2170
ms.date: 03/11/2022
targetos: Windows
description: 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wwan.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: WWAN_READY_INFO_REV2_PRE2170, *PWWAN_READY_INFO_PRE2170
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_READY_INFO_REV2_PRE2170
 - PWWAN_READY_INFO_PRE2170
 - WWAN_READY_INFO_REV2_PRE2170
f1_keywords:
 - _WWAN_READY_INFO_REV2_PRE2170
 - wwan/_WWAN_READY_INFO_REV2_PRE2170
 - PWWAN_READY_INFO_PRE2170
 - wwan/PWWAN_READY_INFO_PRE2170
 - WWAN_READY_INFO_REV2_PRE2170
 - wwan/WWAN_READY_INFO_REV2_PRE2170
dev_langs:
 - c++
helpviewer_keywords:
 - _WWAN_READY_INFO_REV2_PRE2170
---

## -description

The **WWAN_READY_INFO_REV2_PRE2170** structure is the older version of the [**WWAN_READY_INFO**](ns-wwan-_wwan_ready_info.md) structure, previous to Windows 11.

## -struct-fields

### -field ReadyState

The ready-state of the device.

### -field EmergencyMode

The emergency mode of the device. For more information, see <a href="/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_emergency_mode">WWAN_EMERGENCY_MODE</a>.

### -field SubscriberId

A NULL-terminated string of digits that represents the identity of the subscriber.

For GSM-based devices, this member represents the International Mobile Subscriber Identity (IMSI) string (up to 15 digits in length).

For CDMA-based devices, this represents the Mobile Identification Number (MIN) string or the International Roaming MIN (IRM) string (both 10 digits in length).

Miniport drivers must specify this string when the device ready-state changes to <b>WwanReadyStateInitialized</b>. Miniport drivers should also specify this string when the device ready-state changes to <b>WwanReadyStateBadSim</b>, <b>WwanReadyStateFailure</b>, or <b>WwanReadyStateDeviceLocked</b>, if possible, for identification purposes.

For single-carrier multi-mode functions, the GSM <b>SubscriberId</b> format must be used.  This does not apply to multi-carrier multi-mode functions as the <b>SubscriberId</b> may change.

### -field SimIccId

A NULL-terminated string of digits that represents the International Circuit Card (ICC) ID of the SIM. The ICC ID varies from between 15 to 20 digits in length and is represented in alphanumeric characters. Miniport drivers must specify this string when the device ready-state changes to <b>WwanReadyStateInitialized</b> and also when the device is locked, waiting for entry of PIN1 and PUK1 keys.

Miniport drivers must specify this value for all devices where <b>WwanCellularClass</b> equals <b>WwanCellularClassGsm</b>. Miniport drivers of CDMA-based devices must specify this value for devices where <b>SimClass</b> equals <b>WwanSimClassSimRemovable</b>.

### -field CdmaShortMsgSize

The SMS character length that is supported by the network or the device, whichever is less, if the device is CDMA-based.

CDMA-based devices that support SMS should specify their carrier-specific maximum SMS character length to be greater than WWAN_CDMA_SHORT_MSG_SIZE_UNKNOWN and less than WWAN_CDMA_SHORT_MSG_SIZE_MAX.

CDMA-based devices that do not support SMS should set this member to WWAN_CDMA_SHORT_MSG_SIZE_UNKNOWN.

This member does not apply to GSM-based devices. Miniport drivers of GSM-based devices should specify WWAN_CDMA_SHORT_MSG_SIZE_UNKNOWN.

### -field TNListHeader

A list of telephone numbers (TNs) that are assigned to the subscriber identity.

Each element in the list is a string of WCHARs, with a fixed size of WWAN_TN_LEN.

Each TN stored in a list element is a NULL-terminated value.

In GSM-based devices the TNs are called Mobile Station ISDN Number (MSISDNs). In CDMA-based devices they are called Mobile Directory Numbers (MDNs).

Miniport drivers should not specify this value until the device ready-state changes to <b>WwanReadyStateInitialized</b>.

### -field StatusFlags

SIM status flags.

|Value|Meaning|
|---|---|
|WWAN_READY_STATUS_MASK_IS_ESIM 0x00000001| **0**: The current SIM is not an eSIM. **1**: The current SIM is an eSIM. Valid only when the ReadyState is MBIMSubscriberReadyStateInitialized or MBIMSubscriberReadyStateNoEsimProfile.|
|WWAN_READY_STATUS_MASK_SIM_REMOVABILITY_KNOWN 0x00000002|**0**: SIM removability is unknown. **1**: SIM removability is known.|
|WWAN_READY_STATUS_MASK_SIM_FORMFACTOR 0x00000004|**0**: The current SIM is embedded. **1**: The current SIM is removable.Valid only when the ReadyState is MBIMSubscriberReadyStateInitialized, MBIMSubscriberReadyStateNoEsimProfile, or MBIMSubscriberReadyStateDeviceLocked.|
|WWAN_READY_STATUS_MASK_SIM_SLOT_ACTIVE 0x00000008| **0**: The indication came from the currently inactive slot. **1**: The indication came from the currently active slot. This bit may be set independent of the WWAN_READY_STATUS_MASK_MASKS_IS_VALID bit.|
|WWAN_READY_STATUS_MASK_MASKS_IS_VALID 0x80000000|Indicates whether other status bits (except for WWAN_READY_STATUS_MASK_SIM_SLOT_ACTIVE) are invalid. If the bit is **0**, other bits are invalid and should be ignored. If the bit is **1**, other status bits are valid.

## -remarks

## -see-also

[**WWAN_READY_INFO**](ns-wwan-_wwan_ready_info.md)