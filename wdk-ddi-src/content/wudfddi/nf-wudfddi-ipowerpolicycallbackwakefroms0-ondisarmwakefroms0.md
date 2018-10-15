---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0
title: IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0
author: windows-driver-content
description: A driver's OnDisarmWakeFromS0 event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the system working state (S0).
old-location: wdf\ipowerpolicycallbackwakefroms0_ondisarmwakefroms0.htm
tech.root: wdf
ms.assetid: 04c1eecd-c87f-45c5-be7b-0fbd8e114594
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPowerPolicyCallbackWakeFromS0 interface,OnDisarmWakeFromS0 method, IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0, IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0, OnDisarmWakeFromS0, OnDisarmWakeFromS0 method, OnDisarmWakeFromS0 method,IPowerPolicyCallbackWakeFromS0 interface, UMDFDeviceObjectRef_f12fda31-6979-43bf-af04-e46814728ed4.xml, umdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0, wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0, wudfddi/IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IPowerPolicyCallbackWakeFromS0.OnDisarmWakeFromS0
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnDisarmWakeFromS0</b> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



None.




## -remarks



Your driver must provide an <b>OnDisarmWakeFromS0</b> callback function if the driver supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556815">IPowerPolicyCallbackWakeFromS0</a> interface. 

If the driver provides an <b>OnDisarmWakeFromS0</b> callback function, the framework calls it after the bus driver determines that an event has awakened the device, and after the bus driver subsequently completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <b>OnDisarmWakeFromS0</b> callback function, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556822">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a> callback functions.

The <b>OnDisarmWakeFromS0</b> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power is lowered.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/ca36eee5-482c-4cfe-a515-be9d3743e241">PnP and Power Management Scenarios in UMDF</a>.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556815">IPowerPolicyCallbackWakeFromS0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556817">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556822">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a>
 

 

