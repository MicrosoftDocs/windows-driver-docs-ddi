---
UID: NF:wdfdevice.WDF_DEVICE_STATE_INIT
title: WDF_DEVICE_STATE_INIT function
author: windows-driver-content
description: The WDF_DEVICE_STATE_INIT function initializes a driver's WDF_DEVICE_STATE structure.
old-location: wdf\wdf_device_state_init.htm
tech.root: wdf
ms.assetid: f8c040aa-bfa0-4b74-ad0a-8796f1cfc4b8
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectGeneralRef_702c7f79-a50f-4115-ba93-82388ccbf063.xml, WDF_DEVICE_STATE_INIT, WDF_DEVICE_STATE_INIT function, kmdf.wdf_device_state_init, wdf.wdf_device_state_init, wdfdevice/WDF_DEVICE_STATE_INIT
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_DEVICE_STATE_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# WDF_DEVICE_STATE_INIT function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WDF_DEVICE_STATE_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551284">WDF_DEVICE_STATE</a> structure.


## -parameters




### -param PnpDeviceState [out]

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551284">WDF_DEVICE_STATE</a> structure.


## -returns



None




## -remarks



The <b>WDF_DEVICE_STATE_INIT</b> function initializes all of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551284">WDF_DEVICE_STATE</a> structure's <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a>-typed members to <b>WdfUseDefault</b>.


#### Examples

For a code example that uses <b>WDF_DEVICE_STATE_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546884">WdfDeviceSetDeviceState</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551284">WDF_DEVICE_STATE</a>
 

 

