---
UID: NS:netdispumdddi.MIRACAST_SESSION_INFO
title: MIRACAST_SESSION_INFO
author: windows-driver-content
description: Contains info on a wireless display (Miracast) connected session.
old-location: display\miracast_session_info.htm
old-project: display
ms.assetid: 48F3CB86-5181-4E1E-9E7F-88FB2CD3640A
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.miracast_session_info, netdispumdddi/MIRACAST_SESSION_INFO, MIRACAST_SESSION_INFO union [Display Devices], MIRACAST_SESSION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	Netdispumdddi.h
apiname:
-	MIRACAST_SESSION_INFO
product: Windows
targetos: Windows
req.typenames: MIRACAST_SESSION_INFO
---

# MIRACAST_SESSION_INFO structure


## -description


Contains info on a wireless display (Miracast) connected session.


## -syntax


````
typedef union {
  struct {
    UINT MonitorConnected  :1;
    UINT ReducedModeListDueToBandwidth  :1;
    UINT Reserved  :30;
  };
  UINT Value;
} MIRACAST_SESSION_INFO;
````


## -struct-fields




### -field MonitorConnected

If set, the monitor (the source) is connected to a Miracast sink.


### -field ReducedModeListDueToBandwidth

If set, the user-mode driver has reduced the modes exposed to the operating system based on the current suggested encode rate.


### -field Reserved

Reserved for system use and should be set to zero.


### -field Value

Holds a 32-bit value that identifies the Miracast connected session.

