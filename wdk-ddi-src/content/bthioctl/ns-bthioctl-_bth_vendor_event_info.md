---
UID: NS:bthioctl._BTH_VENDOR_EVENT_INFO
title: _BTH_VENDOR_EVENT_INFO (bthioctl.h)
description: The BTH_VENDOR_EVENT_INFO structure specifies the buffer that is associated with the GUID_BLUETOOTH_HCI_VENDOR_EVENT GUID.
old-location: bltooth\bth_vendor_event_info.htm
tech.root: bltooth
ms.assetid: 796f9d91-5c75-4a05-a997-0d5beb7d9fca
ms.date: 04/27/2018
keywords: ["BTH_VENDOR_EVENT_INFO structure"]
ms.keywords: "*PBTH_VENDOR_EVENT_INFO, BTH_VENDOR_EVENT_INFO, BTH_VENDOR_EVENT_INFO structure [Bluetooth Devices], PBTH_VENDOR_EVENT_INFO, PBTH_VENDOR_EVENT_INFO structure pointer [Bluetooth Devices], _BTH_VENDOR_EVENT_INFO, bltooth.bth_vendor_event_info, bth_ref_039b7b82-a08d-41a4-9566-2a5192a23ac2.xml, bthioctl/BTH_VENDOR_EVENT_INFO, bthioctl/PBTH_VENDOR_EVENT_INFO"
f1_keywords:
 - "bthioctl/BTH_VENDOR_EVENT_INFO"
 - "BTH_VENDOR_EVENT_INFO"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Available in Windows Vista, and later versions of Windows.
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
- bthioctl.h
api_name:
- BTH_VENDOR_EVENT_INFO
targetos: Windows
req.typenames: BTH_VENDOR_EVENT_INFO, *PBTH_VENDOR_EVENT_INFO
---

# _BTH_VENDOR_EVENT_INFO structure


## -description


The BTH_VENDOR_EVENT_INFO structure specifies the buffer that is associated with the
  GUID_BLUETOOTH_HCI_VENDOR_EVENT GUID.


## -struct-fields




### -field BthAddress

The address of the local radio that is associated with the event.


### -field EventSize

The size, in bytes, of the event buffer. The size includes the event header.


### -field EventInfo

A UCHAR array for the event buffer. The buffer includes the event header.


## -remarks



The BTH_VENDOR_EVENT_INFO structure contains data that is associated with a
    GUID_BLUETOOTH_HCI_VENDOR_EVENT event.

An application or driver that registers for notifications for the GUID_BTHPORT_DEVICE_INTERFACE GUID
    receives the WM_DEVICECHANGE message that has 
    <i>wParam</i> set to DBT_CUSTOMEVENT and the event GUID set to GUID_BLUETOOTH_HCI_VENDOR_EVENT.



