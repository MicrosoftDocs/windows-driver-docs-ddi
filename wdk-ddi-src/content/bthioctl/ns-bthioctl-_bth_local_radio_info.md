---
UID: NS:bthioctl._BTH_LOCAL_RADIO_INFO
title: _BTH_LOCAL_RADIO_INFO (bthioctl.h)
description: The BTH_LOCAL_RADIO_INFO structure contains information about the local Bluetooth system and radio.
old-location: bltooth\bth_local_radio_info.htm
tech.root: bltooth
ms.assetid: 288863ca-1a11-456f-8d6b-b429668c2bf2
ms.date: 04/27/2018
keywords: ["_BTH_LOCAL_RADIO_INFO structure"]
ms.keywords: "*PBTH_LOCAL_RADIO_INFO, BTH_LOCAL_RADIO_INFO, BTH_LOCAL_RADIO_INFO structure [Bluetooth Devices], PBTH_LOCAL_RADIO_INFO, PBTH_LOCAL_RADIO_INFO structure pointer [Bluetooth Devices], _BTH_LOCAL_RADIO_INFO, bltooth.bth_local_radio_info, bth_structs_8d140abe-9333-4e54-b55b-4ebbd3e1fca3.xml, bthioctl/BTH_LOCAL_RADIO_INFO, bthioctl/PBTH_LOCAL_RADIO_INFO"
f1_keywords:
 - "bthioctl/BTH_LOCAL_RADIO_INFO"
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
- BTH_LOCAL_RADIO_INFO
product:
- Windows
targetos: Windows
req.typenames: BTH_LOCAL_RADIO_INFO, *PBTH_LOCAL_RADIO_INFO
---

# _BTH_LOCAL_RADIO_INFO structure


## -description


The BTH_LOCAL_RADIO_INFO structure contains information about the local Bluetooth system and
  radio.


## -struct-fields




### -field localInfo

A 
     <a href="https://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure that contains
     information about the local radio.


### -field flags

A flag that indicates the state of the local radio. Both flags can be set at the same time.
     Possible values include:
     

LOCAL_RADIO_DISCOVERABLE





LOCAL_RADIO_CONNECTABLE


### -field hciRevision

The minor version of the host controller interface (HCI).


### -field hciVersion

The major version of the HCI.


### -field radioInfo

A 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_radio_info">BTH_RADIO_INFO</a> structure that contains
     information about the local radio device.


## -remarks



The 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_get_local_info">IOCTL_BTH_GET_LOCAL_INFO</a> call's
    output buffer contains the information about the local Bluetooth system and radio.




## -see-also




<a href="https://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_radio_info">BTH_RADIO_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_get_local_info">IOCTL_BTH_GET_LOCAL_INFO</a>
 

 

