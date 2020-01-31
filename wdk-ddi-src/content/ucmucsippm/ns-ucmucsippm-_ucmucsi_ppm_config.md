---
UID: NS:ucmucsippm._UCMUCSI_PPM_CONFIG
title: _UCMUCSI_PPM_CONFIG (ucmucsippm.h)
tech.root: usbref
description: Stores configuration information required to create a Platform Policy Manager (PPM). 
ms.assetid: bb47ac45-b623-4512-89ff-cb434ca4d2ef
ms.date: 09/30/2018
f1_keywords:
 - "ucmucsippm/_UCMUCSI_PPM_CONFIG"
ms.keywords: _UCMUCSI_PPM_CONFIG, UCMUCSI_PPM_CONFIG, *PUCMUCSI_PPM_CONFIG, 
req.header: ucmucsippm.h
req.include-header: UcmUcsiCx.h
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.27
req.umdf-ver: N/A
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: UCMUCSI_PPM_CONFIG, *PUCMUCSI_PPM_CONFIG
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- ucmucsippm.h
api_name: 
- _UCMUCSI_PPM_CONFIG
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# _UCMUCSI_PPM_CONFIG structure

## -description
Stores configuration information required to create a Platform Policy Manager (PPM). Initialize this structure by calling [**UCMUCSI_PPM_CONFIG_INIT**](nf-ucmucsippm-ucmucsi_ppm_config_init.md). This structure is used in the [**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md) call.

## -struct-fields

### -field Size
 
### -field UsbDeviceControllerEnabled
A boolean value that indicates whether or not to enable the device controller.  

### -field ConnectorCollectionHandle
The **ConnectorCollectionHandle** member must be set to the handle retrieved in a previous call to [**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md).

## -remarks

## -see-also

[**UcmUcsiPpmCreate**](nf-ucmucsippm-ucmucsippmcreate.md)
[**UcmUcsiConnectorCollectionCreate**](nf-ucmucsippm-ucmucsiconnectorcollectioncreate.md)
