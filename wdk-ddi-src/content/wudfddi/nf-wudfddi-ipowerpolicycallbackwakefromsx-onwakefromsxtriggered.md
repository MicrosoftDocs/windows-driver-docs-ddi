---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromSx.OnWakeFromSxTriggered
title: IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered
author: windows-driver-content
description: A driver's OnWakeFromSxTriggered event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.
old-location: wdf\ipowerpolicycallbackwakefromsx_onwakefromsxtriggered.htm
tech.root: wdf
ms.assetid: b2379f2d-61a0-4741-a375-c17b95b0faf6
ms.date: 2/26/2018
ms.keywords: IPowerPolicyCallbackWakeFromSx interface,OnWakeFromSxTriggered method, IPowerPolicyCallbackWakeFromSx.OnWakeFromSxTriggered, IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered, OnWakeFromSxTriggered, OnWakeFromSxTriggered method, OnWakeFromSxTriggered method,IPowerPolicyCallbackWakeFromSx interface, UMDFDeviceObjectRef_a92e7dc1-2f1e-4da5-ae71-f57160aa22a0.xml, umdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered, wdf.ipowerpolicycallbackwakefromsx_onwakefromsxtriggered, wudfddi/IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered
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
-	IPowerPolicyCallbackWakeFromSx.OnWakeFromSxTriggered
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnWakeFromSxTriggered</b> event callback function informs the driver that its device, which had previously entered a low-power device state because system power was reduced, might have triggered a wake signal.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



None.




## -remarks



Your driver must provide an <b>OnWakeFromSxTriggered</b> callback function if the driver supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556825">IPowerPolicyCallbackWakeFromSx</a> interface. 

If the driver has registered this callback, the framework calls it after calling the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> callback function and before calling the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <b>OnWakeFromSxTriggered</b> callback function will not be called even though the driver's device triggered a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up-in-umdf-drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556825">IPowerPolicyCallbackWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556826">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a>
 

 

