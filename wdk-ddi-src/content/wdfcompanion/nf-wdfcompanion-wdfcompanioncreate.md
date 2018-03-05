---
UID: NF:wdfcompanion.WdfCompanionCreate
title: WdfCompanionCreate function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfcompanioncreate.htm
old-project: wdf
ms.assetid: 78b9eccf-34ef-40ae-b7fc-6fa8400f8c2a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfCompanionCreate, WdfCompanionCreate method, wdf.wdfcompanioncreate, wdfcompanion/WdfCompanionCreate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfcompanion.h
api_name:
-	WdfCompanionCreate
product: Windows
targetos: Windows
req.typenames: WDF_TASK_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# WdfCompanionCreate function


## -description



			For internal use only.


## -syntax


````
NTSTATUS WdfCompanionCreate(
  _Inout_  PWDFDEVICE_INIT        *DeviceInit,
  _In_opt_ PWDF_OBJECT_ATTRIBUTES DeviceAttributes,
  _Out_    WDFCOMPANION           *Companion
);
````


## -parameters




### -param DeviceInit [in, out]


### -param DeviceAttributes [in, optional]


### -param Companion [out]

