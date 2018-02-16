---
UID: NS:wdfcompanion._WDF_COMPANION_EVENT_CALLBACKS
title: "_WDF_COMPANION_EVENT_CALLBACKS"
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdf_companion_event_callbacks.htm
old-project: wdf
ms.assetid: 6a9c5420-1847-4145-aea5-9e9c58d86ea1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: "_WDF_COMPANION_EVENT_CALLBACKS, WDF_COMPANION_EVENT_CALLBACKS, wdf.wdf_companion_event_callbacks, PWDF_COMPANION_EVENT_CALLBACKS, PWDF_COMPANION_EVENT_CALLBACKS structure pointer, *PWDF_COMPANION_EVENT_CALLBACKS, wdfcompanion/WDF_COMPANION_EVENT_CALLBACKS, wdfcompanion/PWDF_COMPANION_EVENT_CALLBACKS, WDF_COMPANION_EVENT_CALLBACKS structure"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfcompanion.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.23
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
-	wdfcompanion.h
apiname:
-	WDF_COMPANION_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: WDF_COMPANION_EVENT_CALLBACKS, *PWDF_COMPANION_EVENT_CALLBACKS
req.product: Windows 10 or later.
---

# _WDF_COMPANION_EVENT_CALLBACKS structure


## -description


For internal use only.


## -syntax


````
typedef struct _WDF_COMPANION_EVENT_CALLBACKS {
  ULONG                                   Size;
  PFN_WDF_COMPANION_PRE_D0_ENTRY          EvtCompanionPreD0Entry;
  PFN_WDF_COMPANION_POST_D0_EXIT          EvtCompanionPostD0Exit;
  PFN_WDF_COMPANION_PRE_PREPARE_HARDWARE  EvtCompanionPrePrepareHardware;
  PFN_WDF_COMPANION_POST_RELEASE_HARDWARE EvtCompanionPostReleaseHardware;
} WDF_COMPANION_EVENT_CALLBACKS, *PWDF_COMPANION_EVENT_CALLBACKS;
````


## -struct-fields




### -field Size


### -field EvtCompanionPreD0Entry


### -field EvtCompanionPostD0Exit


### -field EvtCompanionPrePrepareHardware


### -field EvtCompanionPostReleaseHardware

