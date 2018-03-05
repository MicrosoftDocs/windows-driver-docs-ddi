---
UID: NF:winsplp.InitializeMonitorEx
title: InitializeMonitorEx function
author: windows-driver-content
description: "."
old-location: print\initializemonitorex.htm
old-project: print
ms.assetid: 1a619b27-4367-419c-985f-588e3f556425
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: InitializeMonitorEx, InitializeMonitorEx function [Print Devices], print.initializemonitorex, spoolfnc_ffa71296-8b2a-48b3-a2c7-9765b9d7aed1.xml, winsplp/InitializeMonitorEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	InitializeMonitorEx
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# InitializeMonitorEx function


## -description





## -syntax


````
BOOL WINAPI InitializeMonitorEx(
  _In_  LPWSTR    pRegistryRoot,
  _Out_ LPMONITOR pMonitor
);
````


## -parameters




### -param pRegistryRoot [in]


### -param pMonitor [out]

