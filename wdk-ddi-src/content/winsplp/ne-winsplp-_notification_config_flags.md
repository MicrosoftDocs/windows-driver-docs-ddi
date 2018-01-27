---
UID: NE:winsplp._NOTIFICATION_CONFIG_FLAGS
title: _NOTIFICATION_CONFIG_FLAGS
author: windows-driver-content
description: .
old-location: print\notification_config_flags.htm
old-project: print
ms.assetid: B53AB706-D780-4E29-A531-51D3A9041D24
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winsplp/NOTIFICATION_CONFIG_FLAGS, winsplp/NOTIFICATION_CONFIG_EVENT_TRIGGER, NOTIFICATION_CONFIG_REGISTER_CALLBACK, winsplp/NOTIFICATION_CONFIG_CREATE_EVENT, NOTIFICATION_CONFIG_EVENT_TRIGGER, _NOTIFICATION_CONFIG_FLAGS, NOTIFICATION_CONFIG_ASYNC_CHANNEL, NOTIFICATION_CONFIG_FLAGS enumeration [Print Devices], winsplp/NOTIFICATION_CONFIG_REGISTER_CALLBACK, NOTIFICATION_CONFIG_CREATE_EVENT, print.notification_config_flags, winsplp/NOTIFICATION_CONFIG_ASYNC_CHANNEL, NOTIFICATION_CONFIG_FLAGS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: winsplp.h
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Winsplp.h
apiname: 
-	NOTIFICATION_CONFIG_FLAGS
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# _NOTIFICATION_CONFIG_FLAGS enumeration


## -description





## -syntax


````
typedef enum _NOTIFICATION_CONFIG_FLAGS { 
  NOTIFICATION_CONFIG_CREATE_EVENT       = 1 << 0,
  NOTIFICATION_CONFIG_REGISTER_CALLBACK  = 1 << 1,
  NOTIFICATION_CONFIG_EVENT_TRIGGER      = 1 << 2,
  NOTIFICATION_CONFIG_ASYNC_CHANNEL      = 1 << 3
} NOTIFICATION_CONFIG_FLAGS;
````


## -enum-fields




### -field NOTIFICATION_CONFIG_CREATE_EVENT



### -field NOTIFICATION_CONFIG_REGISTER_CALLBACK



### -field NOTIFICATION_CONFIG_EVENT_TRIGGER



### -field NOTIFICATION_CONFIG_ASYNC_CHANNEL


