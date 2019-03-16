---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromSx.OnDisarmWakeFromSx
title: IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx (wudfddi.h)
description: A driver's OnDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\ipowerpolicycallbackwakefromsx_ondisarmwakefromsx.htm
tech.root: wdf
ms.assetid: 0e2f42af-3eb7-4957-be91-4f31d2d558c2
ms.date: 02/26/2018
ms.keywords: IPowerPolicyCallbackWakeFromSx interface,OnDisarmWakeFromSx method, IPowerPolicyCallbackWakeFromSx.OnDisarmWakeFromSx, IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx, OnDisarmWakeFromSx, OnDisarmWakeFromSx method, OnDisarmWakeFromSx method,IPowerPolicyCallbackWakeFromSx interface, UMDFDeviceObjectRef_65152bfc-4855-40ba-ab0d-abfc2415441d.xml, umdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx, wdf.ipowerpolicycallbackwakefromsx_ondisarmwakefromsx, wudfddi/IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPowerPolicyCallbackWakeFromSx.OnDisarmWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnDisarmWakeFromSx</b> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556917">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



None.




## -remarks



Your driver must provide an <b>OnDisarmWakeFromSx</b> callback function if the driver supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556825">IPowerPolicyCallbackWakeFromSx</a> interface. 

If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <b>OnDisarmWakeFromSx</b> callback function, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff556833">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a> callback functions.

The <b>OnDisarmWakeFromSx</b> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/ca36eee5-482c-4cfe-a515-be9d3743e241">PnP and Power Management Scenarios in UMDF</a>.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up-in-umdf-drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556825">IPowerPolicyCallbackWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556826">IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556833">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a>
 

 

