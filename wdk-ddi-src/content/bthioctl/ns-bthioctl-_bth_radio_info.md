---
UID: NS:bthioctl._BTH_RADIO_INFO
title: _BTH_RADIO_INFO (bthioctl.h)
description: The BTH_RADIO_INFO structure contains information about a remote radio.
old-location: bltooth\bth_radio_info.htm
tech.root: bltooth
ms.assetid: 24e28912-13d1-460f-8d32-78bb3715adc6
ms.date: 04/27/2018
keywords: ["BTH_RADIO_INFO structure"]
ms.keywords: "*PBTH_RADIO_INFO, BTH_RADIO_INFO, BTH_RADIO_INFO structure [Bluetooth Devices], PBTH_RADIO_INFO, PBTH_RADIO_INFO structure pointer [Bluetooth Devices], _BTH_RADIO_INFO, bltooth.bth_radio_info, bth_structs_5fa8e736-47a7-4ba5-bd40-f375ac6db8af.xml, bthioctl/BTH_RADIO_INFO, bthioctl/PBTH_RADIO_INFO"
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
targetos: Windows
req.typenames: BTH_RADIO_INFO, *PBTH_RADIO_INFO
f1_keywords:
 - _BTH_RADIO_INFO
 - bthioctl/_BTH_RADIO_INFO
 - PBTH_RADIO_INFO
 - bthioctl/PBTH_RADIO_INFO
 - BTH_RADIO_INFO
 - bthioctl/BTH_RADIO_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bthioctl.h
api_name:
 - BTH_RADIO_INFO
---

# _BTH_RADIO_INFO structure


## -description

The BTH_RADIO_INFO structure contains information about a remote radio.

## -struct-fields

### -field lmpSupportedFeatures

A bitmap of Link Management Protocol (LMP) features that are supported by the local radio.

### -field mfg

The identification of the manufacturer.

### -field lmpSubversion

The minor version number for the LMP that is used by the local radio.

### -field lmpVersion

The major version number for the LMP that is used by the local radio.

## -remarks

The BTH_RADIO_INFO structure is returned as part of the output buffer of 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_get_local_info">IOCTL_BTH_GET_LOCAL_INFO</a>. The local
    radio information is returned in the 
    <b>radioInfo</b> member of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ns-bthioctl-_bth_local_radio_info">BTH_LOCAL_RADIO_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/bthioctl/ni-bthioctl-ioctl_bth_get_local_info">IOCTL_BTH_GET_LOCAL_INFO</a>

