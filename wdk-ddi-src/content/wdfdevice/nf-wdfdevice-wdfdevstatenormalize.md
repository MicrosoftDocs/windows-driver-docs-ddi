---
UID: NF:wdfdevice.WdfDevStateNormalize
title: WdfDevStateNormalize function (wdfdevice.h)
description: The WdfDevStateNormalize method removes extra bits from a specified framework state machine value so that the driver can use the value as an index into an array of machine states.
old-location: wdf\wdfdevstatenormalize.htm
tech.root: wdf
ms.assetid: 0243de8b-0f47-4f0a-af25-beb6365386dd
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_24d4e166-f4b0-4696-b775-62d0df565a8a.xml, WdfDevStateNormalize, WdfDevStateNormalize method, kmdf.wdfdevstatenormalize, wdf.wdfdevstatenormalize, wdfdevice/WdfDevStateNormalize
f1_keywords:
 - "wdfdevice/WdfDevStateNormalize"
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
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfDevStateNormalize
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfDevStateNormalize function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfDevStateNormalize</b> method removes extra bits from a specified framework state machine value so that the driver can use the value as an index into an array of machine states.


## -parameters




### -param State [in]

A state machine value that is returned from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepnpstate">WdfDeviceGetDevicePnpState</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerstate">WdfDeviceGetDevicePowerState</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegetdevicepowerpolicystate">WdfDeviceGetDevicePowerPolicyState</a>.


## -returns



<b>WdfDevStateNormalize</b> returns the specified <i>State</i> value with extra bits removed.



