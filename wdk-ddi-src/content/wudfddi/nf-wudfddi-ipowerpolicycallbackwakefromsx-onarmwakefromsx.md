---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromSx.OnArmWakeFromSx
title: IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx (wudfddi.h)
description: A driver's OnArmWakeFromSx event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state.
old-location: wdf\ipowerpolicycallbackwakefromsx_onarmwakefromsx.htm
tech.root: wdf
ms.assetid: 98350b75-aa25-4b3f-ad6c-3038111b8a48
ms.date: 02/26/2018
ms.keywords: IPowerPolicyCallbackWakeFromSx interface,OnArmWakeFromSx method, IPowerPolicyCallbackWakeFromSx.OnArmWakeFromSx, IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx, OnArmWakeFromSx, OnArmWakeFromSx method, OnArmWakeFromSx method,IPowerPolicyCallbackWakeFromSx interface, UMDFDeviceObjectRef_36d2ec5a-4244-499b-9ff3-117704e0ac78.xml, umdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx, wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx, wudfddi/IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx
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
- IPowerPolicyCallbackWakeFromSx.OnArmWakeFromSx
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnArmWakeFromSx</b> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and the system to enter its working state (S0). 


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfdevice">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



If the operation is successful, the <b>OnArmWakeFromSx</b> callback function must return S_OK or another status value for which SUCCEEDED(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which SUCCEEDED(<i>status</i>) equals <b>FALSE</b>.

If SUCCEEDED(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefromsx-ondisarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a> callback function. (The framework does not report a device failure to the PnP manager.) 




## -remarks



Your driver must provide an <b>OnArmWakeFromSx</b> callback function if the driver supports the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefromsx">IPowerPolicyCallbackWakeFromSx</a> interface. 

This callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The kernel-mode bus driver handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If a driver has registered an <b>OnArmWakeFromSx</b> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/sending-a-wait-wake-irp">wait/wake IRP</a> on behalf of the driver. 

The process occurs in the following sequence:

<ol>
<li>
The framework determines that the system is about to enter a low-power system state.

</li>
<li>
The framework calls the driver's <b>OnArmWakeFromSx</b> callback function.

</li>
<li>
The framework asks the driver for the device's bus to lower the device's power.

</li>
</ol>
Immediately before a device enters a low-power state, the framework calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipnpcallback-ond0exit">IPnpCallback::OnD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/pnp-and-power-management-scenarios-in-umdf">PnP and Power Management Scenarios in UMDF</a>.

You do not need to provide an <b>OnArmWakeFromSx</b> callback function if your device does not require special hardware operations that enable the device to trigger a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/supporting-system-wake-up-in-umdf-drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-ipowerpolicycallbackwakefromsx">IPowerPolicyCallbackWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefromsx-ondisarmwakefromsx">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nf-wudfddi-ipowerpolicycallbackwakefromsx-onwakefromsxtriggered">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a>
 

 

