---
UID: NF:wdfdevice.WdfDevStateNormalize
title: WdfDevStateNormalize function
author: windows-driver-content
description: The WdfDevStateNormalize method removes extra bits from a specified framework state machine value so that the driver can use the value as an index into an array of machine states.
old-location: wdf\wdfdevstatenormalize.htm
old-project: wdf
ms.assetid: 0243de8b-0f47-4f0a-af25-beb6365386dd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_24d4e166-f4b0-4696-b775-62d0df565a8a.xml, WdfDevStateNormalize, WdfDevStateNormalize method, kmdf.wdfdevstatenormalize, wdf.wdfdevstatenormalize, wdfdevice/WdfDevStateNormalize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDevStateNormalize
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDevStateNormalize function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDevStateNormalize</b> method removes extra bits from a specified framework state machine value so that the driver can use the value as an index into an array of machine states.


## -syntax


````
ULONG WdfDevStateNormalize(
  _In_ ULONG State
);
````


## -parameters




### -param State [in]

A state machine value that is returned from <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepnpstate.md">WdfDeviceGetDevicePnpState</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerstate.md">WdfDeviceGetDevicePowerState</a>, or <a href="..\wdfdevice\nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md">WdfDeviceGetDevicePowerPolicyState</a>.


## -returns



<b>WdfDevStateNormalize</b> returns the specified <i>State</i> value with extra bits removed.



