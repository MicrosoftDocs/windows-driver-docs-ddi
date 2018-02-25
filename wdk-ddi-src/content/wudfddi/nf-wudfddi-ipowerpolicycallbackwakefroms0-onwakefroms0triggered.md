---
UID: NF:wudfddi.IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered
title: IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered method
author: windows-driver-content
description: A driver's OnWakeFromS0Triggered event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.
old-location: wdf\ipowerpolicycallbackwakefroms0_onwakefroms0triggered.htm
old-project: wdf
ms.assetid: ebcd31f9-79cd-4c43-8cac-231ff97f269e
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., 0, :, C, F, I, IPowerPolicyCallbackWakeFromS0, IPowerPolicyCallbackWakeFromS0 interface, OnWakeFromS0Triggered method, IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered, O, OnWakeFromS0Triggered method, OnWakeFromS0Triggered method, IPowerPolicyCallbackWakeFromS0 interface, OnWakeFromS0Triggered,IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered, P, S, T, UMDFDeviceObjectRef_52f89758-227c-4849-83ac-30826d2d36d0.xml, W, a, b, c, d, e, g, i, k, l, m, n, o, r, umdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered, w, wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered, wudfddi/IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered, y"
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
-	IPowerPolicyCallbackWakeFromS0.OnWakeFromS0Triggered
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnWakeFromS0Triggered</b> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.


## -syntax


````
void OnWakeFromS0Triggered(
  [in] IWDFDevice *pWdfDevice
);
````


## -parameters




### -param pWdfDevice [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfdevice.md">IWDFDevice</a> interface of the device object that represents one of the driver's devices.


## -returns



None.




## -remarks



Your driver must provide an <b>OnWakeFromS0Triggered</b> callback function if the driver supports the <a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefroms0.md">IPowerPolicyCallbackWakeFromS0</a> interface. 

If the driver provides this callback function, the framework calls the function after it calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556799">IPnpCallback::OnD0Entry</a> callback function and before it calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556819">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a> callback function.

System hardware (BIOSes, motherboards, bus adapters) can sometimes drop a wake signal before the bus driver detects it, even though the signal wakes up the system. In such cases, the driver's <b>OnWakeFromS0Triggered</b> callback function will not be called even though the driver's device triggered a wake signal.

For more information about this callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/supporting-idle-power-down-in-umdf-drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556817">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556819">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a>



<a href="..\wudfddi\nn-wudfddi-ipowerpolicycallbackwakefroms0.md">IPowerPolicyCallbackWakeFromS0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

