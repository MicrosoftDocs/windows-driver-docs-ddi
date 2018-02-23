---
UID: NF:poscx.PosCxCleanupEvents
title: PosCxCleanupEvents function
author: windows-driver-content
description: PosCxCleanupEvents is called to clean up all pending events for a given caller, identified by the open instance.
old-location: pos\poscxcleanupevents.htm
old-project: pos
ms.assetid: AD97BA14-8786-47A2-B551-2DB6FC7F83A8
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: pos.poscxcleanupevents, PosCxCleanupEvents function, PosCxCleanupEvents, poscx/PosCxCleanupEvents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	poscx.h
apiname:
-	PosCxCleanupEvents
product: Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---

# PosCxCleanupEvents function


## -description


      PosCxCleanupEvents is called to clean up all pending events for a given  

      caller, identified by the open instance.


## -syntax


````
VOID PosCxCleanupEvents(
  _In_ WDFDEVICE     device,
  _In_ WDFFILEOBJECT fileObject
);
````


## -parameters




### -param device [in]

A handle to a framework device object that represents the device.


### -param fileObject [in]

A handle to a framework file object for which all pending events should be 

          cleaned up.


## -returns



This function does not return a value.



