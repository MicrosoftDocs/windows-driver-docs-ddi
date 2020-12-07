---
UID: NS:ucmmanager._UCM_MANAGER_CONFIG
title: _UCM_MANAGER_CONFIG (ucmmanager.h)
description: Describes the configuration options for the UCM Manager. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_manager_config.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCM_MANAGER_CONFIG structure"]
ms.keywords: "*PUCM_MANAGER_CONFIG, PUCM_MANAGER_CONFIG, PUCM_MANAGER_CONFIG structure pointer [Buses], UCM_MANAGER_CONFIG, UCM_MANAGER_CONFIG structure [Buses], _UCM_MANAGER_CONFIG, buses.ucm_manager_config, ucmmanager/PUCM_MANAGER_CONFIG, ucmmanager/UCM_MANAGER_CONFIG"
req.header: ucmmanager.h
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
targetos: Windows
req.typenames: UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
f1_keywords:
 - _UCM_MANAGER_CONFIG
 - ucmmanager/_UCM_MANAGER_CONFIG
 - PUCM_MANAGER_CONFIG
 - ucmmanager/PUCM_MANAGER_CONFIG
 - UCM_MANAGER_CONFIG
 - ucmmanager/UCM_MANAGER_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmmanager.h
api_name:
 - UCM_MANAGER_CONFIG
---

# _UCM_MANAGER_CONFIG structure


## -description

Describes the configuration options for the UCM Manager. An initialized <b>UCM_MANAGER_CONFIG</b> structure is an input parameter value to   <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucminitializedevice">UcmInitializeDevice</a>.

## -struct-fields

### -field Size

Size of the <b>UCM_MANAGER_CONFIG</b> structure. Initialize this structure by calling <a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_manager_config_init">UCM_MANAGER_CONFIG_INIT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmmanager/nf-ucmmanager-ucm_manager_config_init">UCM_MANAGER_CONFIG_INIT</a>
