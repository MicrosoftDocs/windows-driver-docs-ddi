---
UID: NS:wwan._WWAN_READY_INFO
title: _WWAN_READY_INFO (wwan.h)
description: The WWAN_READY_INFO structure represents the ready-state of the MB device.
old-location: netvista\wwan_ready_info.htm
tech.root: netvista
ms.assetid: 6db8730e-a1da-428b-9938-fd9f3f71283a
ms.date: 05/02/2018
ms.keywords: "*PWWAN_READY_INFO, PWWAN_READY_INFO, PWWAN_READY_INFO structure pointer [Network Drivers Starting with Windows Vista], WWAN_READY_INFO, WWAN_READY_INFO structure [Network Drivers Starting with Windows Vista], WwanRef_8ab0bf23-8ad9-4786-bf5e-013a23d9c16e.xml, _WWAN_READY_INFO, netvista.wwan_ready_info, wwan/PWWAN_READY_INFO, wwan/WWAN_READY_INFO"
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
- wwan.h
api_name:
- WWAN_READY_INFO
product:
- Windows
targetos: Windows
req.typenames: WWAN_READY_INFO, *PWWAN_READY_INFO
---

# _WWAN_READY_INFO structure


## -description


The WWAN_READY_INFO structure represents the ready-state of the MB device.


## -struct-fields




### -field ReadyState

The ready-state of the device.


### -field EmergencyMode

The emergency mode of the device. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_emergency_mode">WWAN_EMERGENCY_MODE</a>.


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


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndiswwan/ns-ndiswwan-_ndis_wwan_ready_info">NDIS_WWAN_READY_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_emergency_mode">WWAN_EMERGENCY_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wwan/ne-wwan-_wwan_ready_state">WWAN_READY_STATE</a>
 

 

