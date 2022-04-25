---
UID: NF:acxevents.ACX_PNPEVENT_CONFIG_INIT
tech.root: audio
title: ACX_PNPEVENT_CONFIG_INIT
ms.date: 11/03/2021
targetos: Windows
description: The ACX_PNPEVENT_CONFIG_INIT function initializes an ACX_PNPEVENT_CONFIG structure.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxevents.h
api_name:
 - ACX_PNPEVENT_CONFIG_INIT
f1_keywords:
 - ACX_PNPEVENT_CONFIG_INIT
 - acxevents/ACX_PNPEVENT_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_PNPEVENT_CONFIG_INIT** function initializes an [ACX_PNPEVENT_CONFIG](ns-acxevents-acx_pnpevent_config.md) structure. No inputs are used with this function.

## -parameters

### -param Config

An initialized [ACX_PNPEVENT_CONFIG structure](ns-acxevents-acx_pnpevent_config.md) that will be used to describe the configuration of the event.

## -remarks

### Example

The example shows the use of the ACX_PNPEVENT_CONFIG_INIT.

TBD - Anything else we should show here?

```cpp

    ACX_PNPEVENT_CONFIG             audioModuleEventCfg;

    ACX_PNPEVENT_CONFIG_INIT(&audioModuleEventCfg);
```


## -see-also

- [acxevents.h header](index.md)

TBD - Please review this topic