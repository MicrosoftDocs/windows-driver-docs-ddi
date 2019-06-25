---
UID: NS:ufxproprietarycharger._UFX_PROPRIETARY_CHARGER
title: _UFX_PROPRIETARY_CHARGER (ufxproprietarycharger.h)
description: Describes the proprietary charger's device power requirements.
old-location: buses\ufx_proprietary_charger.htm
tech.root: usbref
ms.assetid: FAAEDAFE-69A8-4092-8301-DB159FD3583D
ms.date: 05/07/2018
ms.keywords: "*PUFX_PROPRIETARY_CHARGER, PUFX_PROPRIETARY_CHARGER, PUFX_PROPRIETARY_CHARGER structure pointer [Buses], UFX_PROPRIETARY_CHARGER, UFX_PROPRIETARY_CHARGER structure [Buses], _UFX_PROPRIETARY_CHARGER, buses.ufx_proprietary_charger, ufxproprietarycharger/PUFX_PROPRIETARY_CHARGER, ufxproprietarycharger/UFX_PROPRIETARY_CHARGER"
ms.topic: struct
req.header: ufxproprietarycharger.h
req.include-header: 
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
- ufxproprietarycharger.h
api_name:
- UFX_PROPRIETARY_CHARGER
product:
- Windows
targetos: Windows
req.typenames: UFX_PROPRIETARY_CHARGER, *PUFX_PROPRIETARY_CHARGER
---

# _UFX_PROPRIETARY_CHARGER structure


## -description


Describes the proprietary charger's device power requirements.


## -struct-fields




### -field ChargerId

Charger identifier used to identify a specific type of charger.


### -field DxState

The minimum required device power state when it is connected, indicated by one of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/ne-wudfddi-_device_power_state">DEVICE_POWER_STATE</a>-typed flags.

