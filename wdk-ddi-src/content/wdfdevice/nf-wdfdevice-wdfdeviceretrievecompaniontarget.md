---
UID: NF:wdfdevice.WdfDeviceRetrieveCompanionTarget
title: WdfDeviceRetrieveCompanionTarget function
author: windows-driver-content
description: For internal use only.
old-location: wdf\wdfdeviceretrievecompaniontarget.htm
old-project: wdf
ms.assetid: 2ca34fb7-72c1-4253-ad5b-bc829a1ba540
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfDeviceRetrieveCompanionTarget, WdfDeviceRetrieveCompanionTarget method, wdf.wdfdeviceretrievecompaniontarget, wdfdevice/WdfDeviceRetrieveCompanionTarget
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.23
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WdfDeviceRetrieveCompanionTarget
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceRetrieveCompanionTarget function


## -description


For internal use only.


## -syntax


````
NTSTATUS WdfDeviceRetrieveCompanionTarget(
  _In_  WDFDEVICE          Device,
  _Out_ WDFCOMPANIONTARGET *CompanionTarget
);
````


## -parameters




### -param Device [in]


### -param CompanionTarget [out]

