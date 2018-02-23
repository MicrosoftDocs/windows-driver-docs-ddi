---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromSx.OnArmWakeFromSx
title: IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx method
author: windows-driver-content
description: A driver's OnArmWakeFromSx event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state.
old-location: wdf\ipowerpolicycallbackwakefromsx_onarmwakefromsx.htm
old-project: wdf
ms.assetid: 98350b75-aa25-4b3f-ad6c-3038111b8a48
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wudfddi/IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx, OnArmWakeFromSx, IPowerPolicyCallbackWakeFromSx, umdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx, wdf.ipowerpolicycallbackwakefromsx_onarmwakefromsx, OnArmWakeFromSx method, IPowerPolicyCallbackWakeFromSx interface, IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx, UMDFDeviceObjectRef_36d2ec5a-4244-499b-9ff3-117704e0ac78.xml, OnArmWakeFromSx method, IPowerPolicyCallbackWakeFromSx interface, OnArmWakeFromSx method
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
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IPowerPolicyCallbackWakeFromSx.OnArmWakeFromSx
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnArmWakeFromSx</b> event callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state. The wake signal causes the device to enter its working state (D0) and the system to enter its working state (S0). 


## -syntax


````
HRESULT OnArmWakeFromSx(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



If the operation is successful, the <b>OnArmWakeFromSx</b> callback function must return S_OK or another status value for which SUCCEEDED(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which SUCCEEDED(<i>status</i>) equals <b>FALSE</b>.

If SUCCEEDED(status) equals <b>FALSE</b>, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a> callback function. (The framework does not report a device failure to the PnP manager.) 




## -remarks



Your driver must provide an <b>OnArmWakeFromSx</b> callback function if the driver supports the <a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a> interface. 

This callback function handles device-specific operations that are needed to enable the device to detect an external event that triggers a wake signal on the bus. The kernel-mode bus driver handles bus-specific operations, such as enabling the PCI bus's Power Management Event (PME) signal.

If a driver has registered an <b>OnArmWakeFromSx</b> callback function, the framework calls it while the device is still in the D0 device power state, before the bus driver lowers the device's power state but after the framework has sent a <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a> on behalf of the driver. 

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
Immediately before a device enters a low-power state, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556803">IPnpCallback::OnD0Exit</a> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/ca36eee5-482c-4cfe-a515-be9d3743e241">PnP and Power Management Scenarios in UMDF</a>.

You do not need to provide an <b>OnArmWakeFromSx</b> callback function if your device does not require special hardware operations that enable the device to trigger a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-system-wake-up-in-umdf-drivers">Supporting System Wake-Up in UMDF-based Drivers</a>.




## -see-also

<a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefromsx.md">IPowerPolicyCallbackWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556828">IPowerPolicyCallbackWakeFromSx::OnDisarmWakeFromSx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556833">IPowerPolicyCallbackWakeFromSx::OnWakeFromSxTriggered</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPowerPolicyCallbackWakeFromSx::OnArmWakeFromSx method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

